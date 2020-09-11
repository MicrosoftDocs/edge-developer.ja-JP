---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalPointerInfo
ms.openlocfilehash: db966ad087e22bc6b8d3865c416f8feba15e434a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011403"
---
# <span data-ttu-id="4e63f-104">0.9.579-インターフェイス ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="4e63f-104">0.9.579 - interface ICoreWebView2ExperimentalPointerInfo</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="4e63f-105">これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="4e63f-105">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="4e63f-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4e63f-106">Summary</span></span>

 <span data-ttu-id="4e63f-107">Members</span><span class="sxs-lookup"><span data-stu-id="4e63f-107">Members</span></span>                        | <span data-ttu-id="4e63f-108">説明</span><span class="sxs-lookup"><span data-stu-id="4e63f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4e63f-109">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-109">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="4e63f-110">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-110">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="4e63f-111">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-111">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="4e63f-112">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-112">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="4e63f-113">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="4e63f-113">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="4e63f-114">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-114">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="4e63f-115">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-115">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="4e63f-116">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-116">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-117">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-117">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="4e63f-118">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-118">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="4e63f-119">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-119">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="4e63f-120">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-120">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="4e63f-121">get_InputData</span><span class="sxs-lookup"><span data-stu-id="4e63f-121">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="4e63f-122">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-122">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="4e63f-123">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="4e63f-123">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="4e63f-124">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-124">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="4e63f-125">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-125">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="4e63f-126">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-126">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="4e63f-127">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-127">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="4e63f-128">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-128">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="4e63f-129">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-129">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="4e63f-130">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-130">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="4e63f-131">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="4e63f-131">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="4e63f-132">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-132">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-133">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="4e63f-133">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="4e63f-134">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-134">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="4e63f-135">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="4e63f-135">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="4e63f-136">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-136">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="4e63f-137">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-137">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="4e63f-138">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-138">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="4e63f-139">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-139">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="4e63f-140">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-140">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-141">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-141">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="4e63f-142">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-142">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="4e63f-143">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-143">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="4e63f-144">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-144">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="4e63f-145">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-145">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="4e63f-146">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-146">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="4e63f-147">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="4e63f-147">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="4e63f-148">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-148">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="4e63f-149">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-149">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="4e63f-150">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-150">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="4e63f-151">get_Time</span><span class="sxs-lookup"><span data-stu-id="4e63f-151">get_Time</span></span>](#get_time) | <span data-ttu-id="4e63f-152">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-152">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="4e63f-153">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="4e63f-153">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="4e63f-154">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-154">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="4e63f-155">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-155">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="4e63f-156">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-156">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="4e63f-157">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-157">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="4e63f-158">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-158">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="4e63f-159">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-159">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="4e63f-160">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-160">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="4e63f-161">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="4e63f-161">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="4e63f-162">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-162">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-163">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-163">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="4e63f-164">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-164">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="4e63f-165">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-165">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="4e63f-166">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-166">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="4e63f-167">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-167">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="4e63f-168">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-168">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="4e63f-169">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="4e63f-169">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="4e63f-170">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-170">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="4e63f-171">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-171">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="4e63f-172">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-172">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-173">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-173">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="4e63f-174">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-174">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="4e63f-175">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-175">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="4e63f-176">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-176">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="4e63f-177">put_InputData</span><span class="sxs-lookup"><span data-stu-id="4e63f-177">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="4e63f-178">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-178">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="4e63f-179">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="4e63f-179">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="4e63f-180">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-180">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="4e63f-181">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-181">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="4e63f-182">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-182">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="4e63f-183">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-183">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="4e63f-184">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-184">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="4e63f-185">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-185">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="4e63f-186">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-186">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="4e63f-187">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="4e63f-187">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="4e63f-188">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-188">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-189">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="4e63f-189">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="4e63f-190">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-190">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="4e63f-191">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="4e63f-191">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="4e63f-192">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-192">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="4e63f-193">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-193">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="4e63f-194">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-194">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="4e63f-195">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-195">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="4e63f-196">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-196">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-197">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-197">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="4e63f-198">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-198">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="4e63f-199">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-199">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="4e63f-200">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-200">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="4e63f-201">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-201">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="4e63f-202">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-202">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="4e63f-203">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="4e63f-203">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="4e63f-204">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-204">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="4e63f-205">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-205">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="4e63f-206">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-206">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="4e63f-207">put_Time</span><span class="sxs-lookup"><span data-stu-id="4e63f-207">put_Time</span></span>](#put_time) | <span data-ttu-id="4e63f-208">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-208">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="4e63f-209">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="4e63f-209">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="4e63f-210">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-210">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="4e63f-211">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-211">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="4e63f-212">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-212">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="4e63f-213">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-213">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="4e63f-214">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-214">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="4e63f-215">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-215">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="4e63f-216">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-216">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="4e63f-217">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="4e63f-217">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="4e63f-218">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-218">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="4e63f-219">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-219">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="4e63f-220">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-220">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="4e63f-221">この例では、3つのフィールドをすべて受け取り、HWND やハンドルなどの win32 固有のデータ型を除外しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-221">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="4e63f-222">注: sourceDevice は使用されますが、PointerDeviceRect と DisplayRect で sourceDevice の既存のユースケースをカバーすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-222">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="4e63f-223">また、point または rect のいずれかの場所が、webview の物理座標であることが想定されているという大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="4e63f-223">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="4e63f-224">つまり、webview と DPI のスケーリングが適用された相対的な座標です。</span><span class="sxs-lookup"><span data-stu-id="4e63f-224">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="4e63f-225">Members</span><span class="sxs-lookup"><span data-stu-id="4e63f-225">Members</span></span>

#### <span data-ttu-id="4e63f-226">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-226">get_ButtonChangeKind</span></span> 

<span data-ttu-id="4e63f-227">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-227">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="4e63f-228">パブリック HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="4e63f-228">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="4e63f-229">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-229">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="4e63f-230">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-230">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-231">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-231">get_DisplayRect</span></span> 

<span data-ttu-id="4e63f-232">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-232">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="4e63f-233">パブリック HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayrect)</span><span class="sxs-lookup"><span data-stu-id="4e63f-233">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="4e63f-234">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="4e63f-234">get_FrameId</span></span> 

<span data-ttu-id="4e63f-235">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-235">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="4e63f-236">パブリック HRESULT [get_FrameId](#get_frameid)(UINT32 \* フレーム id)</span><span class="sxs-lookup"><span data-stu-id="4e63f-236">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="4e63f-237">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-237">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-238">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-238">get_HimetricLocation</span></span> 

<span data-ttu-id="4e63f-239">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-239">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-240">パブリック HRESULT [get_HimetricLocation](#get_himetriclocation)(ポイント \* himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="4e63f-240">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="4e63f-241">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-241">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-242">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-242">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="4e63f-243">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-243">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="4e63f-244">パブリック HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(ポイント \* himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="4e63f-244">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="4e63f-245">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-245">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-246">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-246">get_HistoryCount</span></span> 

<span data-ttu-id="4e63f-247">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-247">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="4e63f-248">パブリック HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="4e63f-248">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="4e63f-249">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-249">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-250">get_InputData</span><span class="sxs-lookup"><span data-stu-id="4e63f-250">get_InputData</span></span> 

<span data-ttu-id="4e63f-251">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-251">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="4e63f-252">パブリック HRESULT [get_InputData](#get_inputdata)(INT32 \* inputdata)</span><span class="sxs-lookup"><span data-stu-id="4e63f-252">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="4e63f-253">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-253">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-254">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="4e63f-254">get_KeyStates</span></span> 

<span data-ttu-id="4e63f-255">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-255">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="4e63f-256">パブリック HRESULT [get_KeyStates](#get_keystates)(DWORD \* keystates)</span><span class="sxs-lookup"><span data-stu-id="4e63f-256">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="4e63f-257">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-257">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-258">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-258">get_PenFlags</span></span> 

<span data-ttu-id="4e63f-259">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-259">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="4e63f-260">パブリック HRESULT [get_PenFlags](#get_penflags)(UINT32 \* ペンフラグ)</span><span class="sxs-lookup"><span data-stu-id="4e63f-260">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="4e63f-261">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-261">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="4e63f-262">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-262">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-263">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-263">get_PenMask</span></span> 

<span data-ttu-id="4e63f-264">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-264">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="4e63f-265">パブリック HRESULT [get_PenMask](#get_penmask)(UINT32 \* ペンマスク)</span><span class="sxs-lookup"><span data-stu-id="4e63f-265">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="4e63f-266">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-266">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="4e63f-267">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-267">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-268">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-268">get_PenPressure</span></span> 

<span data-ttu-id="4e63f-269">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-269">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="4e63f-270">パブリック HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* の筆圧)</span><span class="sxs-lookup"><span data-stu-id="4e63f-270">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="4e63f-271">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-271">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-272">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="4e63f-272">get_PenRotation</span></span> 

<span data-ttu-id="4e63f-273">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-273">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-274">パブリック HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* の回転回転)</span><span class="sxs-lookup"><span data-stu-id="4e63f-274">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="4e63f-275">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-275">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-276">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="4e63f-276">get_PenTiltX</span></span> 

<span data-ttu-id="4e63f-277">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-277">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="4e63f-278">パブリック HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="4e63f-278">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="4e63f-279">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-279">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-280">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="4e63f-280">get_PenTiltY</span></span> 

<span data-ttu-id="4e63f-281">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-281">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="4e63f-282">パブリック HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="4e63f-282">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="4e63f-283">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-283">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-284">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-284">get_PerformanceCount</span></span> 

<span data-ttu-id="4e63f-285">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-285">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="4e63f-286">パブリック HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="4e63f-286">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="4e63f-287">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-287">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-288">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-288">get_PixelLocation</span></span> 

<span data-ttu-id="4e63f-289">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-289">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-290">パブリック HRESULT [get_PixelLocation](#get_pixellocation)(ポイント \* ピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="4e63f-290">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="4e63f-291">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-291">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-292">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-292">get_PixelLocationRaw</span></span> 

<span data-ttu-id="4e63f-293">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-293">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="4e63f-294">パブリック HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(ポイント \* ピクセルの場所 raw)</span><span class="sxs-lookup"><span data-stu-id="4e63f-294">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="4e63f-295">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-295">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-296">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-296">get_PointerDeviceRect</span></span> 

<span data-ttu-id="4e63f-297">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-297">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="4e63f-298">パブリック HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="4e63f-298">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="4e63f-299">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-299">get_PointerFlags</span></span> 

<span data-ttu-id="4e63f-300">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-300">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="4e63f-301">パブリック HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="4e63f-301">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="4e63f-302">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-302">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="4e63f-303">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-303">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-304">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="4e63f-304">get_PointerId</span></span> 

<span data-ttu-id="4e63f-305">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-305">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="4e63f-306">パブリック HRESULT [get_PointerId](#get_pointerid)(UINT32 \* ポインター id)</span><span class="sxs-lookup"><span data-stu-id="4e63f-306">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="4e63f-307">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-307">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-308">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-308">get_PointerKind</span></span> 

<span data-ttu-id="4e63f-309">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-309">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="4e63f-310">パブリック HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="4e63f-310">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="4e63f-311">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-311">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="4e63f-312">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-312">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="4e63f-313">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4e63f-313">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="4e63f-314">get_Time</span><span class="sxs-lookup"><span data-stu-id="4e63f-314">get_Time</span></span> 

<span data-ttu-id="4e63f-315">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-315">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="4e63f-316">パブリック HRESULT [get_Time](#get_time)(DWORD \* 時刻)</span><span class="sxs-lookup"><span data-stu-id="4e63f-316">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="4e63f-317">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-317">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-318">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="4e63f-318">get_TouchContact</span></span> 

<span data-ttu-id="4e63f-319">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-319">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="4e63f-320">パブリック HRESULT [get_TouchContact](#get_touchcontact)(RECT \* TouchContact)</span><span class="sxs-lookup"><span data-stu-id="4e63f-320">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="4e63f-321">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-321">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-322">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-322">get_TouchContactRaw</span></span> 

<span data-ttu-id="4e63f-323">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-323">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="4e63f-324">パブリック HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="4e63f-324">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="4e63f-325">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-325">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-326">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-326">get_TouchFlags</span></span> 

<span data-ttu-id="4e63f-327">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-327">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="4e63f-328">パブリック HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="4e63f-328">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="4e63f-329">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-329">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="4e63f-330">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-330">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-331">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-331">get_TouchMask</span></span> 

<span data-ttu-id="4e63f-332">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-332">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="4e63f-333">パブリック HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* TouchMask)</span><span class="sxs-lookup"><span data-stu-id="4e63f-333">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="4e63f-334">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-334">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="4e63f-335">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-335">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-336">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="4e63f-336">get_TouchOrientation</span></span> 

<span data-ttu-id="4e63f-337">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-337">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-338">パブリック HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="4e63f-338">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="4e63f-339">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-339">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-340">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-340">get_TouchPressure</span></span> 

<span data-ttu-id="4e63f-341">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-341">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="4e63f-342">パブリック HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="4e63f-342">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="4e63f-343">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-343">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-344">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-344">put_ButtonChangeKind</span></span> 

<span data-ttu-id="4e63f-345">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-345">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="4e63f-346">パブリック HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="4e63f-346">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="4e63f-347">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-347">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="4e63f-348">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-348">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-349">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-349">put_DisplayRect</span></span> 

<span data-ttu-id="4e63f-350">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-350">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="4e63f-351">パブリック HRESULT [put_DisplayRect](#put_displayrect)(RECT displayrect)</span><span class="sxs-lookup"><span data-stu-id="4e63f-351">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="4e63f-352">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="4e63f-352">put_FrameId</span></span> 

<span data-ttu-id="4e63f-353">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-353">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="4e63f-354">パブリック HRESULT [put_FrameId](#put_frameid)(UINT32 フレーム id)</span><span class="sxs-lookup"><span data-stu-id="4e63f-354">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="4e63f-355">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-355">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-356">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-356">put_HimetricLocation</span></span> 

<span data-ttu-id="4e63f-357">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-357">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-358">パブリック HRESULT [put_HimetricLocation](#put_himetriclocation)(ポイント himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="4e63f-358">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="4e63f-359">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-359">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-360">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-360">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="4e63f-361">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-361">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="4e63f-362">パブリック HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(ポイント himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="4e63f-362">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="4e63f-363">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-363">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-364">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-364">put_HistoryCount</span></span> 

<span data-ttu-id="4e63f-365">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-365">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="4e63f-366">パブリック HRESULT [put_HistoryCount](#put_historycount)(UINT32 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="4e63f-366">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="4e63f-367">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-367">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-368">put_InputData</span><span class="sxs-lookup"><span data-stu-id="4e63f-368">put_InputData</span></span> 

<span data-ttu-id="4e63f-369">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-369">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="4e63f-370">パブリック HRESULT [put_InputData](#put_inputdata)(INT32 inputdata)</span><span class="sxs-lookup"><span data-stu-id="4e63f-370">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="4e63f-371">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-371">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-372">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="4e63f-372">put_KeyStates</span></span> 

<span data-ttu-id="4e63f-373">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-373">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="4e63f-374">パブリック HRESULT [put_KeyStates](#put_keystates)(DWORD keystates)</span><span class="sxs-lookup"><span data-stu-id="4e63f-374">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="4e63f-375">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-375">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-376">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-376">put_PenFlags</span></span> 

<span data-ttu-id="4e63f-377">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-377">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="4e63f-378">パブリック HRESULT [put_PenFlags](#put_penflags)(UINT32 のフラグ)</span><span class="sxs-lookup"><span data-stu-id="4e63f-378">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="4e63f-379">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-379">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="4e63f-380">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-380">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-381">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-381">put_PenMask</span></span> 

<span data-ttu-id="4e63f-382">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-382">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="4e63f-383">パブリック HRESULT [put_PenMask](#put_penmask)(UINT32 のマスク)</span><span class="sxs-lookup"><span data-stu-id="4e63f-383">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="4e63f-384">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-384">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="4e63f-385">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-385">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-386">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-386">put_PenPressure</span></span> 

<span data-ttu-id="4e63f-387">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-387">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="4e63f-388">パブリック HRESULT [put_PenPressure](#put_penpressure)(UINT32)</span><span class="sxs-lookup"><span data-stu-id="4e63f-388">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="4e63f-389">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-389">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-390">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="4e63f-390">put_PenRotation</span></span> 

<span data-ttu-id="4e63f-391">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-391">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-392">パブリック HRESULT [put_PenRotation](#put_penrotation)(UINT32 の回転)</span><span class="sxs-lookup"><span data-stu-id="4e63f-392">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="4e63f-393">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-393">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-394">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="4e63f-394">put_PenTiltX</span></span> 

<span data-ttu-id="4e63f-395">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-395">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="4e63f-396">パブリック HRESULT [put_PenTiltX](#put_pentiltx)(INT32 PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="4e63f-396">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="4e63f-397">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-397">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-398">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="4e63f-398">put_PenTiltY</span></span> 

<span data-ttu-id="4e63f-399">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-399">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="4e63f-400">パブリック HRESULT [put_PenTiltY](#put_pentilty)(INT32 PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="4e63f-400">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="4e63f-401">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-401">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-402">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="4e63f-402">put_PerformanceCount</span></span> 

<span data-ttu-id="4e63f-403">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-403">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="4e63f-404">パブリック HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="4e63f-404">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="4e63f-405">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-405">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-406">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="4e63f-406">put_PixelLocation</span></span> 

<span data-ttu-id="4e63f-407">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-407">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-408">パブリック HRESULT [put_PixelLocation](#put_pixellocation)(ポイントピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="4e63f-408">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="4e63f-409">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-409">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-410">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-410">put_PixelLocationRaw</span></span> 

<span data-ttu-id="4e63f-411">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-411">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="4e63f-412">パブリック HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(ポイントのピクセルの位置に raw)</span><span class="sxs-lookup"><span data-stu-id="4e63f-412">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="4e63f-413">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-413">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-414">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="4e63f-414">put_PointerDeviceRect</span></span> 

<span data-ttu-id="4e63f-415">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-415">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="4e63f-416">パブリック HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="4e63f-416">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="4e63f-417">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-417">put_PointerFlags</span></span> 

<span data-ttu-id="4e63f-418">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-418">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="4e63f-419">パブリック HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="4e63f-419">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="4e63f-420">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-420">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="4e63f-421">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-421">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-422">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="4e63f-422">put_PointerId</span></span> 

<span data-ttu-id="4e63f-423">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-423">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="4e63f-424">パブリック HRESULT [put_PointerId](#put_pointerid)(UINT32 ポインター id)</span><span class="sxs-lookup"><span data-stu-id="4e63f-424">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="4e63f-425">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-425">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-426">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="4e63f-426">put_PointerKind</span></span> 

<span data-ttu-id="4e63f-427">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-427">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="4e63f-428">パブリック HRESULT [put_PointerKind](#put_pointerkind)(DWORD ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="4e63f-428">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="4e63f-429">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-429">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="4e63f-430">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-430">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="4e63f-431">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4e63f-431">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="4e63f-432">put_Time</span><span class="sxs-lookup"><span data-stu-id="4e63f-432">put_Time</span></span> 

<span data-ttu-id="4e63f-433">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-433">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="4e63f-434">パブリック HRESULT [put_Time](#put_time)(DWORD 時刻)</span><span class="sxs-lookup"><span data-stu-id="4e63f-434">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="4e63f-435">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-435">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-436">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="4e63f-436">put_TouchContact</span></span> 

<span data-ttu-id="4e63f-437">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-437">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="4e63f-438">パブリック HRESULT [put_TouchContact](#put_touchcontact)(RECT TouchContact)</span><span class="sxs-lookup"><span data-stu-id="4e63f-438">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="4e63f-439">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-439">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-440">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="4e63f-440">put_TouchContactRaw</span></span> 

<span data-ttu-id="4e63f-441">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-441">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="4e63f-442">パブリック HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="4e63f-442">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="4e63f-443">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-443">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-444">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="4e63f-444">put_TouchFlags</span></span> 

<span data-ttu-id="4e63f-445">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-445">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="4e63f-446">パブリック HRESULT [put_TouchFlags](#put_touchflags)(UINT32 TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="4e63f-446">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="4e63f-447">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-447">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="4e63f-448">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-448">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-449">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="4e63f-449">put_TouchMask</span></span> 

<span data-ttu-id="4e63f-450">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-450">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="4e63f-451">パブリック HRESULT [put_TouchMask](#put_touchmask)(UINT32 TouchMask)</span><span class="sxs-lookup"><span data-stu-id="4e63f-451">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="4e63f-452">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-452">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="4e63f-453">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e63f-453">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-454">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="4e63f-454">put_TouchOrientation</span></span> 

<span data-ttu-id="4e63f-455">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-455">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="4e63f-456">パブリック HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="4e63f-456">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="4e63f-457">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-457">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="4e63f-458">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="4e63f-458">put_TouchPressure</span></span> 

<span data-ttu-id="4e63f-459">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e63f-459">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="4e63f-460">パブリック HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="4e63f-460">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="4e63f-461">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4e63f-461">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

