---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2CompositionController
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2CompositionController。
ms.openlocfilehash: 51c6ebb12130632c5fb08e2992caf6ae83a478b1
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012295"
---
# <span data-ttu-id="12b07-104">WebView2 クラス (CoreWebView2CompositionController クラス)</span><span class="sxs-lookup"><span data-stu-id="12b07-104">Microsoft.Web.WebView2.Core.CoreWebView2CompositionController class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="12b07-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="12b07-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="12b07-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="12b07-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="12b07-107">このクラスは、CoreWebView2Controller クラスの拡張機能であり、ビジュアルホストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="12b07-107">This class is an extension of the CoreWebView2Controller class to support visual hosting.</span></span>

## <span data-ttu-id="12b07-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="12b07-108">Summary</span></span>

 <span data-ttu-id="12b07-109">Members</span><span class="sxs-lookup"><span data-stu-id="12b07-109">Members</span></span>                        | <span data-ttu-id="12b07-110">説明</span><span class="sxs-lookup"><span data-stu-id="12b07-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="12b07-111">Cursor</span><span class="sxs-lookup"><span data-stu-id="12b07-111">Cursor</span></span>](#cursor) | <span data-ttu-id="12b07-112">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="12b07-112">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="12b07-113">カーソルが変更されました</span><span class="sxs-lookup"><span data-stu-id="12b07-113">CursorChanged</span></span>](#cursorchanged) | <span data-ttu-id="12b07-114">WebView がカーソルの変更であると判断されたときに、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="12b07-114">The event fires when WebView thinks the cursor should be changed.</span></span>
[<span data-ttu-id="12b07-115">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="12b07-115">RootVisualTarget</span></span>](#rootvisualtarget) | <span data-ttu-id="12b07-116">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="12b07-116">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="12b07-117">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="12b07-117">UIAProvider</span></span>](#uiaprovider) | <span data-ttu-id="12b07-118">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="12b07-118">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="12b07-119">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="12b07-119">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="12b07-120">システムから受け取ったポインター Id を CoreWebView2PointerInfo に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="12b07-120">A helper function to convert a pointerId received from the system into a CoreWebView2PointerInfo.</span></span>
[<span data-ttu-id="12b07-121">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="12b07-121">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="12b07-122">EventKind が CoreWebView2MouseEventKind Wheel または CoreWebView2MouseEventKind の場合は、mouseData はホイールの動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="12b07-122">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="12b07-123">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="12b07-123">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="12b07-124">Sendpointer Input は、CoreWebView2PointerEventKind で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="12b07-124">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

## <span data-ttu-id="12b07-125">Members</span><span class="sxs-lookup"><span data-stu-id="12b07-125">Members</span></span>

#### <span data-ttu-id="12b07-126">Cursor</span><span class="sxs-lookup"><span data-stu-id="12b07-126">Cursor</span></span> 

<span data-ttu-id="12b07-127">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="12b07-127">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="12b07-128">パブリック IntPtr [カーソル](#cursor)</span><span class="sxs-lookup"><span data-stu-id="12b07-128">public IntPtr [Cursor](#cursor)</span></span>

<span data-ttu-id="12b07-129">WM_SETCURSOR でカーソルを設定するか、WebView ~ SetClassLongPtr の対応する親または先祖の HWND を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b07-129">The cursor should be set in WM_SETCURSOR through Mouse.SetCursor or set on the corresponding parent/ancestor HWND of the WebView through SetClassLongPtr.</span></span> <span data-ttu-id="12b07-130">HCURSOR を解放すると、カーソルをすぐに設定するよりも、コピーを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12b07-130">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="12b07-131">カーソルが変更されました</span><span class="sxs-lookup"><span data-stu-id="12b07-131">CursorChanged</span></span> 

<span data-ttu-id="12b07-132">WebView がカーソルの変更であると判断されたときに、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="12b07-132">The event fires when WebView thinks the cursor should be changed.</span></span>

> <span data-ttu-id="12b07-133">< オブジェクト >[カーソルが変更された](#cursorchanged)パブリックイベント EventHandler</span><span class="sxs-lookup"><span data-stu-id="12b07-133">public event EventHandler< object > [CursorChanged](#cursorchanged)</span></span>

<span data-ttu-id="12b07-134">たとえば、マウスカーソルが現在既定のカーソルであり、テキストの上に移動した場合は、IBeam カーソルに変更しようとすることがあります。</span><span class="sxs-lookup"><span data-stu-id="12b07-134">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span> <span data-ttu-id="12b07-135">CoreWebView2MouseEventKind を送信するには、送信者が送信する必要があります。 SendMouseInput API を介して、(CoreWebView2MouseEventKind に加えて) メッセージを移動します。</span><span class="sxs-lookup"><span data-stu-id="12b07-135">It is expected for the developer to send CoreWebView2MouseEventKind.Leave messages (in addition to CoreWebView2MouseEventKind.Move messages) through the SendMouseInput API.</span></span> <span data-ttu-id="12b07-136">これは、カーソルの変更されたイベントを送信する WebView 内に実際にマウスがあることを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="12b07-136">This is to ensure that the mouse is actually within the WebView that sends out CursorChanged events.</span></span>

#### <span data-ttu-id="12b07-137">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="12b07-137">RootVisualTarget</span></span> 

<span data-ttu-id="12b07-138">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="12b07-138">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="12b07-139">パブリックオブジェクト [Rootvisualtarget](#rootvisualtarget)</span><span class="sxs-lookup"><span data-stu-id="12b07-139">public object [RootVisualTarget](#rootvisualtarget)</span></span>

<span data-ttu-id="12b07-140">このビジュアルは、WebView がそのビジュアルツリーを接続する場所です。</span><span class="sxs-lookup"><span data-stu-id="12b07-140">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="12b07-141">アプリでは、このビジュアルを使って、アプリ内で WebView を配置します。</span><span class="sxs-lookup"><span data-stu-id="12b07-141">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="12b07-142">この場合も、アプリでは、境界プロパティを使って WebView のサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b07-142">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="12b07-143">RootVisualTarget プロパティは、IDCompositionVisual または Windows:: UI:: コンポジション:: ContainerVisual とすることができます。</span><span class="sxs-lookup"><span data-stu-id="12b07-143">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="12b07-144">WebView は、プロパティ setter から戻る前に、ビジュアルツリーを提供された visual に接続します。</span><span class="sxs-lookup"><span data-stu-id="12b07-144">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="12b07-145">アプリは、Root Visualtarget プロパティのデバイス設定でコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b07-145">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="12b07-146">RootVisualTarget プロパティは、アプリのビジュアルツリーから WebView を切断するために nullptr に設定されています。</span><span class="sxs-lookup"><span data-stu-id="12b07-146">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span>

#### <span data-ttu-id="12b07-147">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="12b07-147">UIAProvider</span></span> 

<span data-ttu-id="12b07-148">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="12b07-148">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="12b07-149">パブリックオブジェクト [Uiaprovider](#uiaprovider)</span><span class="sxs-lookup"><span data-stu-id="12b07-149">public object [UIAProvider](#uiaprovider)</span></span>

#### <span data-ttu-id="12b07-150">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="12b07-150">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="12b07-151">システムから受け取ったポインター Id を CoreWebView2PointerInfo に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="12b07-151">A helper function to convert a pointerId received from the system into a CoreWebView2PointerInfo.</span></span>

> <span data-ttu-id="12b07-152">パブリック [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(Uint ポインター Id、IntPtr parentwindow、Matrix4x4 transform)</span><span class="sxs-lookup"><span data-stu-id="12b07-152">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(uint PointerId, IntPtr ParentWindow, Matrix4x4 transform)</span></span>

<span data-ttu-id="12b07-153">parentWindow は、WebView を含む HWND です。</span><span class="sxs-lookup"><span data-stu-id="12b07-153">parentWindow is the HWND that contains the WebView.</span></span> <span data-ttu-id="12b07-154">これは、WebView を含む hwnd ツリー内の任意の HWND にすることができます。</span><span class="sxs-lookup"><span data-stu-id="12b07-154">This can be any HWND in the hwnd tree that contains the WebView.</span></span> <span data-ttu-id="12b07-155">CoreWebView2Matrix4x4 は、その HWND から WebView への変換です。</span><span class="sxs-lookup"><span data-stu-id="12b07-155">The CoreWebView2Matrix4x4 is the transform from that HWND to the WebView.</span></span> <span data-ttu-id="12b07-156">返された CoreWebView2PointerInfo は、Sendポインタ Info で使われます。</span><span class="sxs-lookup"><span data-stu-id="12b07-156">The returned CoreWebView2PointerInfo is used in SendPointerInfo.</span></span> <span data-ttu-id="12b07-157">ポインターの型は、ペンまたはタッチである必要があります。または、関数は失敗します。</span><span class="sxs-lookup"><span data-stu-id="12b07-157">The pointer type must be either pen or touch or the function will fail.</span></span>

#### <span data-ttu-id="12b07-158">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="12b07-158">SendMouseInput</span></span> 

<span data-ttu-id="12b07-159">EventKind が CoreWebView2MouseEventKind Wheel または CoreWebView2MouseEventKind の場合は、mouseData はホイールの動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="12b07-159">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="12b07-160">パブリックの void [Sendmouseinput](#sendmouseinput)([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventkind、 [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) Virtualkeys、uint mousedata、ポイントポイント)</span><span class="sxs-lookup"><span data-stu-id="12b07-160">public void [SendMouseInput](#sendmouseinput)([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventKind, [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) virtualKeys, uint mouseData, Point point)</span></span>

<span data-ttu-id="12b07-161">正の値は、ホイールがユーザーによって前方に回転されたことを示します。負の値は、ホイールが背面に回転していることを示します。</span><span class="sxs-lookup"><span data-stu-id="12b07-161">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="12b07-162">ホイールクリックの1つは、120として定義されている WHEEL_DELTA として定義されています。</span><span class="sxs-lookup"><span data-stu-id="12b07-162">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="12b07-163">EventKind が CoreWebView2MouseEventKind XButtonDoubleClick CoreWebView2MouseEventKind Down または CoreWebView2MouseEventKind Up の場合、mouseData は、どの X ボタンが押されたか、離されたかを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b07-163">If eventKind is CoreWebView2MouseEventKind.XButtonDoubleClick CoreWebView2MouseEventKind.XButtonDown, or CoreWebView2MouseEventKind.XButtonUp, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="12b07-164">この値は、最初の X ボタンが押されている場合は1、2番目の X ボタンが押されたとき、または離された場合は1になります。</span><span class="sxs-lookup"><span data-stu-id="12b07-164">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="12b07-165">EventKind が CoreWebView2MouseEventKind の場合は、virtualKeys、mouseData、point がすべてゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b07-165">If eventKind is CoreWebView2MouseEventKind.Leave, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="12b07-166">EventKind がその他の値である場合は、mouseData は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b07-166">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="12b07-167">Point は、WebView のクライアント座標空間に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b07-167">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="12b07-168">WebView から始まり、WebView とホストアプリケーションの外側に移動する可能性のあるマウスイベントを追跡するには、SetCapture と ReleaseCapture の呼び出しをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12b07-168">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="12b07-169">ホバーポップアップを消すには、CoreWebView2MouseEventKind メッセージを送信することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12b07-169">To dismiss hover popups, it is also recommended to send CoreWebView2MouseEventKind.Leave messages.</span></span>

#### <span data-ttu-id="12b07-170">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="12b07-170">SendPointerInput</span></span> 

<span data-ttu-id="12b07-171">Sendpointer Input は、CoreWebView2PointerEventKind で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="12b07-171">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

> <span data-ttu-id="12b07-172">パブリック void [Sendポインタ入力](#sendpointerinput)([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventkind、 [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) ポインタ info)</span><span class="sxs-lookup"><span data-stu-id="12b07-172">public void [SendPointerInput](#sendpointerinput)([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventKind, [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) pointerInfo)</span></span>

<span data-ttu-id="12b07-173">システムからのポインター入力は、最初に CoreWebView2PointerInfo に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b07-173">Any pointer input from the system must be converted into a CoreWebView2PointerInfo first.</span></span>

