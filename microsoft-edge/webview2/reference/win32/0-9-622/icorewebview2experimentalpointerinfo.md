---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalPointerInfo
ms.openlocfilehash: bc35ebaf3f1b5acf12a1d379336cd006f962390e
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012348"
---
# <span data-ttu-id="72c1a-104">インターフェイス ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="72c1a-104">interface ICoreWebView2ExperimentalPointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="72c1a-105">これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="72c1a-105">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="72c1a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="72c1a-106">Summary</span></span>

 <span data-ttu-id="72c1a-107">Members</span><span class="sxs-lookup"><span data-stu-id="72c1a-107">Members</span></span>                        | <span data-ttu-id="72c1a-108">説明</span><span class="sxs-lookup"><span data-stu-id="72c1a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="72c1a-109">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-109">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="72c1a-110">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-110">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="72c1a-111">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-111">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="72c1a-112">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-112">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="72c1a-113">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="72c1a-113">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="72c1a-114">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-114">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="72c1a-115">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-115">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="72c1a-116">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-116">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-117">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-117">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="72c1a-118">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-118">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="72c1a-119">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-119">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="72c1a-120">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-120">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="72c1a-121">get_InputData</span><span class="sxs-lookup"><span data-stu-id="72c1a-121">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="72c1a-122">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-122">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="72c1a-123">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="72c1a-123">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="72c1a-124">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-124">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="72c1a-125">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-125">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="72c1a-126">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-126">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="72c1a-127">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-127">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="72c1a-128">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-128">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="72c1a-129">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-129">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="72c1a-130">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-130">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="72c1a-131">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="72c1a-131">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="72c1a-132">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-132">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-133">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="72c1a-133">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="72c1a-134">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-134">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="72c1a-135">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="72c1a-135">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="72c1a-136">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-136">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="72c1a-137">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-137">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="72c1a-138">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-138">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="72c1a-139">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-139">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="72c1a-140">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-140">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-141">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-141">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="72c1a-142">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-142">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="72c1a-143">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-143">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="72c1a-144">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-144">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="72c1a-145">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-145">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="72c1a-146">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-146">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="72c1a-147">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="72c1a-147">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="72c1a-148">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-148">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="72c1a-149">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-149">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="72c1a-150">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-150">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="72c1a-151">get_Time</span><span class="sxs-lookup"><span data-stu-id="72c1a-151">get_Time</span></span>](#get_time) | <span data-ttu-id="72c1a-152">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-152">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="72c1a-153">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="72c1a-153">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="72c1a-154">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-154">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="72c1a-155">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-155">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="72c1a-156">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-156">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="72c1a-157">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-157">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="72c1a-158">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-158">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="72c1a-159">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-159">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="72c1a-160">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-160">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="72c1a-161">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="72c1a-161">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="72c1a-162">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-162">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-163">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-163">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="72c1a-164">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-164">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="72c1a-165">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-165">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="72c1a-166">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-166">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="72c1a-167">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-167">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="72c1a-168">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-168">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="72c1a-169">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="72c1a-169">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="72c1a-170">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-170">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="72c1a-171">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-171">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="72c1a-172">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-172">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-173">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-173">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="72c1a-174">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-174">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="72c1a-175">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-175">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="72c1a-176">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-176">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="72c1a-177">put_InputData</span><span class="sxs-lookup"><span data-stu-id="72c1a-177">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="72c1a-178">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-178">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="72c1a-179">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="72c1a-179">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="72c1a-180">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-180">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="72c1a-181">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-181">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="72c1a-182">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-182">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="72c1a-183">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-183">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="72c1a-184">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-184">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="72c1a-185">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-185">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="72c1a-186">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-186">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="72c1a-187">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="72c1a-187">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="72c1a-188">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-188">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-189">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="72c1a-189">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="72c1a-190">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-190">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="72c1a-191">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="72c1a-191">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="72c1a-192">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-192">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="72c1a-193">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-193">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="72c1a-194">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-194">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="72c1a-195">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-195">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="72c1a-196">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-196">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-197">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-197">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="72c1a-198">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-198">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="72c1a-199">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-199">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="72c1a-200">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-200">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="72c1a-201">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-201">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="72c1a-202">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-202">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="72c1a-203">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="72c1a-203">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="72c1a-204">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-204">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="72c1a-205">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-205">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="72c1a-206">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-206">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="72c1a-207">put_Time</span><span class="sxs-lookup"><span data-stu-id="72c1a-207">put_Time</span></span>](#put_time) | <span data-ttu-id="72c1a-208">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-208">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="72c1a-209">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="72c1a-209">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="72c1a-210">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-210">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="72c1a-211">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-211">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="72c1a-212">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-212">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="72c1a-213">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-213">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="72c1a-214">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-214">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="72c1a-215">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-215">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="72c1a-216">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-216">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="72c1a-217">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="72c1a-217">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="72c1a-218">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-218">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="72c1a-219">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-219">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="72c1a-220">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-220">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="72c1a-221">この例では、3つのフィールドをすべて受け取り、HWND やハンドルなどの win32 固有のデータ型を除外しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-221">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="72c1a-222">注: sourceDevice は使用されますが、PointerDeviceRect と DisplayRect で sourceDevice の既存のユースケースをカバーすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-222">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="72c1a-223">また、point または rect のいずれかの場所が、webview の物理座標であることが想定されているという大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="72c1a-223">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="72c1a-224">つまり、webview と DPI のスケーリングが適用された相対的な座標です。</span><span class="sxs-lookup"><span data-stu-id="72c1a-224">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="72c1a-225">Members</span><span class="sxs-lookup"><span data-stu-id="72c1a-225">Members</span></span>

#### <span data-ttu-id="72c1a-226">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-226">get_ButtonChangeKind</span></span> 

<span data-ttu-id="72c1a-227">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-227">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="72c1a-228">パブリック HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="72c1a-228">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="72c1a-229">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-229">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="72c1a-230">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-230">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-231">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-231">get_DisplayRect</span></span> 

<span data-ttu-id="72c1a-232">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-232">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="72c1a-233">パブリック HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayrect)</span><span class="sxs-lookup"><span data-stu-id="72c1a-233">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="72c1a-234">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="72c1a-234">get_FrameId</span></span> 

<span data-ttu-id="72c1a-235">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-235">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="72c1a-236">パブリック HRESULT [get_FrameId](#get_frameid)(UINT32 \* フレーム id)</span><span class="sxs-lookup"><span data-stu-id="72c1a-236">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="72c1a-237">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-237">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-238">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-238">get_HimetricLocation</span></span> 

<span data-ttu-id="72c1a-239">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-239">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-240">パブリック HRESULT [get_HimetricLocation](#get_himetriclocation)(ポイント \* himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="72c1a-240">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="72c1a-241">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-241">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-242">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-242">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="72c1a-243">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-243">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="72c1a-244">パブリック HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(ポイント \* himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="72c1a-244">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="72c1a-245">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-245">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-246">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-246">get_HistoryCount</span></span> 

<span data-ttu-id="72c1a-247">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-247">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="72c1a-248">パブリック HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="72c1a-248">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="72c1a-249">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-249">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-250">get_InputData</span><span class="sxs-lookup"><span data-stu-id="72c1a-250">get_InputData</span></span> 

<span data-ttu-id="72c1a-251">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-251">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="72c1a-252">パブリック HRESULT [get_InputData](#get_inputdata)(INT32 \* inputdata)</span><span class="sxs-lookup"><span data-stu-id="72c1a-252">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="72c1a-253">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-253">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-254">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="72c1a-254">get_KeyStates</span></span> 

<span data-ttu-id="72c1a-255">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-255">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="72c1a-256">パブリック HRESULT [get_KeyStates](#get_keystates)(DWORD \* keystates)</span><span class="sxs-lookup"><span data-stu-id="72c1a-256">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="72c1a-257">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-257">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-258">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-258">get_PenFlags</span></span> 

<span data-ttu-id="72c1a-259">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-259">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="72c1a-260">パブリック HRESULT [get_PenFlags](#get_penflags)(UINT32 \* ペンフラグ)</span><span class="sxs-lookup"><span data-stu-id="72c1a-260">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="72c1a-261">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-261">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="72c1a-262">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-262">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-263">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-263">get_PenMask</span></span> 

<span data-ttu-id="72c1a-264">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-264">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="72c1a-265">パブリック HRESULT [get_PenMask](#get_penmask)(UINT32 \* ペンマスク)</span><span class="sxs-lookup"><span data-stu-id="72c1a-265">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="72c1a-266">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-266">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="72c1a-267">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-267">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-268">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-268">get_PenPressure</span></span> 

<span data-ttu-id="72c1a-269">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-269">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="72c1a-270">パブリック HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* の筆圧)</span><span class="sxs-lookup"><span data-stu-id="72c1a-270">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="72c1a-271">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-271">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-272">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="72c1a-272">get_PenRotation</span></span> 

<span data-ttu-id="72c1a-273">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-273">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-274">パブリック HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* の回転回転)</span><span class="sxs-lookup"><span data-stu-id="72c1a-274">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="72c1a-275">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-275">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-276">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="72c1a-276">get_PenTiltX</span></span> 

<span data-ttu-id="72c1a-277">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-277">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="72c1a-278">パブリック HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="72c1a-278">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="72c1a-279">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-279">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-280">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="72c1a-280">get_PenTiltY</span></span> 

<span data-ttu-id="72c1a-281">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-281">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="72c1a-282">パブリック HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="72c1a-282">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="72c1a-283">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-283">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-284">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-284">get_PerformanceCount</span></span> 

<span data-ttu-id="72c1a-285">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-285">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="72c1a-286">パブリック HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="72c1a-286">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="72c1a-287">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-287">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-288">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-288">get_PixelLocation</span></span> 

<span data-ttu-id="72c1a-289">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-289">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-290">パブリック HRESULT [get_PixelLocation](#get_pixellocation)(ポイント \* ピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="72c1a-290">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="72c1a-291">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-291">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-292">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-292">get_PixelLocationRaw</span></span> 

<span data-ttu-id="72c1a-293">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-293">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="72c1a-294">パブリック HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(ポイント \* ピクセルの場所 raw)</span><span class="sxs-lookup"><span data-stu-id="72c1a-294">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="72c1a-295">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-295">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-296">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-296">get_PointerDeviceRect</span></span> 

<span data-ttu-id="72c1a-297">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-297">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="72c1a-298">パブリック HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="72c1a-298">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="72c1a-299">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-299">get_PointerFlags</span></span> 

<span data-ttu-id="72c1a-300">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-300">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="72c1a-301">パブリック HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="72c1a-301">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="72c1a-302">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-302">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="72c1a-303">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-303">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-304">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="72c1a-304">get_PointerId</span></span> 

<span data-ttu-id="72c1a-305">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-305">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="72c1a-306">パブリック HRESULT [get_PointerId](#get_pointerid)(UINT32 \* ポインター id)</span><span class="sxs-lookup"><span data-stu-id="72c1a-306">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="72c1a-307">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-307">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-308">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-308">get_PointerKind</span></span> 

<span data-ttu-id="72c1a-309">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-309">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="72c1a-310">パブリック HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="72c1a-310">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="72c1a-311">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-311">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="72c1a-312">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-312">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="72c1a-313">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="72c1a-313">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="72c1a-314">get_Time</span><span class="sxs-lookup"><span data-stu-id="72c1a-314">get_Time</span></span> 

<span data-ttu-id="72c1a-315">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-315">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="72c1a-316">パブリック HRESULT [get_Time](#get_time)(DWORD \* 時刻)</span><span class="sxs-lookup"><span data-stu-id="72c1a-316">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="72c1a-317">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-317">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-318">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="72c1a-318">get_TouchContact</span></span> 

<span data-ttu-id="72c1a-319">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-319">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="72c1a-320">パブリック HRESULT [get_TouchContact](#get_touchcontact)(RECT \* TouchContact)</span><span class="sxs-lookup"><span data-stu-id="72c1a-320">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="72c1a-321">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-321">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-322">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-322">get_TouchContactRaw</span></span> 

<span data-ttu-id="72c1a-323">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-323">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="72c1a-324">パブリック HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="72c1a-324">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="72c1a-325">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-325">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-326">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-326">get_TouchFlags</span></span> 

<span data-ttu-id="72c1a-327">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-327">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="72c1a-328">パブリック HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="72c1a-328">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="72c1a-329">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-329">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="72c1a-330">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-330">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-331">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-331">get_TouchMask</span></span> 

<span data-ttu-id="72c1a-332">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-332">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="72c1a-333">パブリック HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* TouchMask)</span><span class="sxs-lookup"><span data-stu-id="72c1a-333">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="72c1a-334">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-334">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="72c1a-335">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-335">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-336">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="72c1a-336">get_TouchOrientation</span></span> 

<span data-ttu-id="72c1a-337">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-337">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-338">パブリック HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="72c1a-338">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="72c1a-339">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-339">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-340">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-340">get_TouchPressure</span></span> 

<span data-ttu-id="72c1a-341">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-341">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="72c1a-342">パブリック HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="72c1a-342">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="72c1a-343">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-343">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-344">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-344">put_ButtonChangeKind</span></span> 

<span data-ttu-id="72c1a-345">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-345">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="72c1a-346">パブリック HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="72c1a-346">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="72c1a-347">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-347">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="72c1a-348">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-348">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-349">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-349">put_DisplayRect</span></span> 

<span data-ttu-id="72c1a-350">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-350">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="72c1a-351">パブリック HRESULT [put_DisplayRect](#put_displayrect)(RECT displayrect)</span><span class="sxs-lookup"><span data-stu-id="72c1a-351">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="72c1a-352">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="72c1a-352">put_FrameId</span></span> 

<span data-ttu-id="72c1a-353">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-353">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="72c1a-354">パブリック HRESULT [put_FrameId](#put_frameid)(UINT32 フレーム id)</span><span class="sxs-lookup"><span data-stu-id="72c1a-354">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="72c1a-355">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-355">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-356">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-356">put_HimetricLocation</span></span> 

<span data-ttu-id="72c1a-357">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-357">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-358">パブリック HRESULT [put_HimetricLocation](#put_himetriclocation)(ポイント himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="72c1a-358">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="72c1a-359">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-359">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-360">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-360">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="72c1a-361">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-361">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="72c1a-362">パブリック HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(ポイント himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="72c1a-362">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="72c1a-363">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-363">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-364">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-364">put_HistoryCount</span></span> 

<span data-ttu-id="72c1a-365">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-365">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="72c1a-366">パブリック HRESULT [put_HistoryCount](#put_historycount)(UINT32 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="72c1a-366">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="72c1a-367">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-367">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-368">put_InputData</span><span class="sxs-lookup"><span data-stu-id="72c1a-368">put_InputData</span></span> 

<span data-ttu-id="72c1a-369">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-369">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="72c1a-370">パブリック HRESULT [put_InputData](#put_inputdata)(INT32 inputdata)</span><span class="sxs-lookup"><span data-stu-id="72c1a-370">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="72c1a-371">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-371">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-372">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="72c1a-372">put_KeyStates</span></span> 

<span data-ttu-id="72c1a-373">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-373">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="72c1a-374">パブリック HRESULT [put_KeyStates](#put_keystates)(DWORD keystates)</span><span class="sxs-lookup"><span data-stu-id="72c1a-374">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="72c1a-375">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-375">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-376">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-376">put_PenFlags</span></span> 

<span data-ttu-id="72c1a-377">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-377">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="72c1a-378">パブリック HRESULT [put_PenFlags](#put_penflags)(UINT32 のフラグ)</span><span class="sxs-lookup"><span data-stu-id="72c1a-378">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="72c1a-379">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-379">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="72c1a-380">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-380">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-381">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-381">put_PenMask</span></span> 

<span data-ttu-id="72c1a-382">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-382">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="72c1a-383">パブリック HRESULT [put_PenMask](#put_penmask)(UINT32 のマスク)</span><span class="sxs-lookup"><span data-stu-id="72c1a-383">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="72c1a-384">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-384">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="72c1a-385">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-385">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-386">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-386">put_PenPressure</span></span> 

<span data-ttu-id="72c1a-387">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-387">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="72c1a-388">パブリック HRESULT [put_PenPressure](#put_penpressure)(UINT32)</span><span class="sxs-lookup"><span data-stu-id="72c1a-388">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="72c1a-389">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-389">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-390">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="72c1a-390">put_PenRotation</span></span> 

<span data-ttu-id="72c1a-391">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-391">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-392">パブリック HRESULT [put_PenRotation](#put_penrotation)(UINT32 の回転)</span><span class="sxs-lookup"><span data-stu-id="72c1a-392">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="72c1a-393">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-393">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-394">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="72c1a-394">put_PenTiltX</span></span> 

<span data-ttu-id="72c1a-395">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-395">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="72c1a-396">パブリック HRESULT [put_PenTiltX](#put_pentiltx)(INT32 PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="72c1a-396">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="72c1a-397">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-397">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-398">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="72c1a-398">put_PenTiltY</span></span> 

<span data-ttu-id="72c1a-399">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-399">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="72c1a-400">パブリック HRESULT [put_PenTiltY](#put_pentilty)(INT32 PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="72c1a-400">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="72c1a-401">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-401">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-402">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="72c1a-402">put_PerformanceCount</span></span> 

<span data-ttu-id="72c1a-403">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-403">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="72c1a-404">パブリック HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="72c1a-404">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="72c1a-405">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-405">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-406">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="72c1a-406">put_PixelLocation</span></span> 

<span data-ttu-id="72c1a-407">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-407">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-408">パブリック HRESULT [put_PixelLocation](#put_pixellocation)(ポイントピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="72c1a-408">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="72c1a-409">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-409">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-410">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-410">put_PixelLocationRaw</span></span> 

<span data-ttu-id="72c1a-411">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-411">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="72c1a-412">パブリック HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(ポイントのピクセルの位置に raw)</span><span class="sxs-lookup"><span data-stu-id="72c1a-412">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="72c1a-413">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-413">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-414">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="72c1a-414">put_PointerDeviceRect</span></span> 

<span data-ttu-id="72c1a-415">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-415">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="72c1a-416">パブリック HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="72c1a-416">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="72c1a-417">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-417">put_PointerFlags</span></span> 

<span data-ttu-id="72c1a-418">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-418">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="72c1a-419">パブリック HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="72c1a-419">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="72c1a-420">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-420">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="72c1a-421">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-421">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-422">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="72c1a-422">put_PointerId</span></span> 

<span data-ttu-id="72c1a-423">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-423">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="72c1a-424">パブリック HRESULT [put_PointerId](#put_pointerid)(UINT32 ポインター id)</span><span class="sxs-lookup"><span data-stu-id="72c1a-424">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="72c1a-425">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-425">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-426">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="72c1a-426">put_PointerKind</span></span> 

<span data-ttu-id="72c1a-427">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-427">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="72c1a-428">パブリック HRESULT [put_PointerKind](#put_pointerkind)(DWORD ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="72c1a-428">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="72c1a-429">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-429">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="72c1a-430">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-430">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="72c1a-431">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="72c1a-431">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="72c1a-432">put_Time</span><span class="sxs-lookup"><span data-stu-id="72c1a-432">put_Time</span></span> 

<span data-ttu-id="72c1a-433">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-433">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="72c1a-434">パブリック HRESULT [put_Time](#put_time)(DWORD 時刻)</span><span class="sxs-lookup"><span data-stu-id="72c1a-434">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="72c1a-435">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-435">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-436">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="72c1a-436">put_TouchContact</span></span> 

<span data-ttu-id="72c1a-437">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-437">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="72c1a-438">パブリック HRESULT [put_TouchContact](#put_touchcontact)(RECT TouchContact)</span><span class="sxs-lookup"><span data-stu-id="72c1a-438">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="72c1a-439">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-439">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-440">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="72c1a-440">put_TouchContactRaw</span></span> 

<span data-ttu-id="72c1a-441">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-441">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="72c1a-442">パブリック HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="72c1a-442">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="72c1a-443">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-443">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-444">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="72c1a-444">put_TouchFlags</span></span> 

<span data-ttu-id="72c1a-445">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-445">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="72c1a-446">パブリック HRESULT [put_TouchFlags](#put_touchflags)(UINT32 TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="72c1a-446">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="72c1a-447">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-447">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="72c1a-448">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-448">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-449">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="72c1a-449">put_TouchMask</span></span> 

<span data-ttu-id="72c1a-450">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-450">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="72c1a-451">パブリック HRESULT [put_TouchMask](#put_touchmask)(UINT32 TouchMask)</span><span class="sxs-lookup"><span data-stu-id="72c1a-451">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="72c1a-452">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-452">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="72c1a-453">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="72c1a-453">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-454">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="72c1a-454">put_TouchOrientation</span></span> 

<span data-ttu-id="72c1a-455">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-455">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="72c1a-456">パブリック HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="72c1a-456">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="72c1a-457">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-457">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="72c1a-458">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="72c1a-458">put_TouchPressure</span></span> 

<span data-ttu-id="72c1a-459">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="72c1a-459">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="72c1a-460">パブリック HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="72c1a-460">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="72c1a-461">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="72c1a-461">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

