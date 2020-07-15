---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 887dcd438a89dcff4da239872df4bdb51e90f1f0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880613"
---
# <span data-ttu-id="2be55-104">0.9.515-インターフェイス ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="2be55-104">0.9.515 - interface ICoreWebView2ExperimentalPointerInfo</span></span> 

> [!NOTE]
> <span data-ttu-id="2be55-105">これは、プレリリース SDK バージョン0.9.488 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="2be55-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="2be55-106">これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="2be55-106">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="2be55-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="2be55-107">Summary</span></span>

 <span data-ttu-id="2be55-108">Members</span><span class="sxs-lookup"><span data-stu-id="2be55-108">Members</span></span>                        | <span data-ttu-id="2be55-109">説明</span><span class="sxs-lookup"><span data-stu-id="2be55-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2be55-110">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="2be55-110">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="2be55-111">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-111">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="2be55-112">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="2be55-112">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="2be55-113">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-113">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="2be55-114">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="2be55-114">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="2be55-115">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-115">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="2be55-116">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-116">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="2be55-117">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-117">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="2be55-118">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-118">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="2be55-119">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-119">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="2be55-120">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="2be55-120">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="2be55-121">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-121">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="2be55-122">get_InputData</span><span class="sxs-lookup"><span data-stu-id="2be55-122">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="2be55-123">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-123">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="2be55-124">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="2be55-124">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="2be55-125">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-125">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="2be55-126">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-126">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="2be55-127">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-127">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="2be55-128">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="2be55-128">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="2be55-129">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-129">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="2be55-130">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-130">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="2be55-131">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-131">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="2be55-132">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="2be55-132">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="2be55-133">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-133">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="2be55-134">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="2be55-134">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="2be55-135">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-135">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="2be55-136">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="2be55-136">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="2be55-137">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-137">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="2be55-138">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="2be55-138">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="2be55-139">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-139">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="2be55-140">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-140">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="2be55-141">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-141">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="2be55-142">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-142">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="2be55-143">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-143">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="2be55-144">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="2be55-144">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="2be55-145">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-145">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="2be55-146">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-146">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="2be55-147">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-147">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="2be55-148">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="2be55-148">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="2be55-149">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-149">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="2be55-150">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="2be55-150">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="2be55-151">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-151">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="2be55-152">get_Time</span><span class="sxs-lookup"><span data-stu-id="2be55-152">get_Time</span></span>](#get_time) | <span data-ttu-id="2be55-153">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-153">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="2be55-154">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="2be55-154">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="2be55-155">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-155">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="2be55-156">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-156">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="2be55-157">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-157">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="2be55-158">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-158">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="2be55-159">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-159">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="2be55-160">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="2be55-160">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="2be55-161">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-161">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="2be55-162">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="2be55-162">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="2be55-163">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-163">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="2be55-164">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-164">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="2be55-165">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-165">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="2be55-166">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="2be55-166">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="2be55-167">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-167">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="2be55-168">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="2be55-168">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="2be55-169">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-169">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="2be55-170">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="2be55-170">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="2be55-171">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-171">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="2be55-172">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-172">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="2be55-173">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-173">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="2be55-174">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-174">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="2be55-175">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-175">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="2be55-176">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="2be55-176">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="2be55-177">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-177">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="2be55-178">put_InputData</span><span class="sxs-lookup"><span data-stu-id="2be55-178">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="2be55-179">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-179">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="2be55-180">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="2be55-180">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="2be55-181">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-181">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="2be55-182">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-182">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="2be55-183">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-183">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="2be55-184">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="2be55-184">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="2be55-185">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-185">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="2be55-186">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-186">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="2be55-187">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-187">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="2be55-188">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="2be55-188">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="2be55-189">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-189">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="2be55-190">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="2be55-190">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="2be55-191">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-191">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="2be55-192">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="2be55-192">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="2be55-193">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-193">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="2be55-194">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="2be55-194">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="2be55-195">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-195">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="2be55-196">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-196">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="2be55-197">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-197">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="2be55-198">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-198">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="2be55-199">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-199">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="2be55-200">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="2be55-200">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="2be55-201">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-201">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="2be55-202">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-202">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="2be55-203">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-203">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="2be55-204">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="2be55-204">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="2be55-205">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-205">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="2be55-206">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="2be55-206">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="2be55-207">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-207">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="2be55-208">put_Time</span><span class="sxs-lookup"><span data-stu-id="2be55-208">put_Time</span></span>](#put_time) | <span data-ttu-id="2be55-209">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-209">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="2be55-210">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="2be55-210">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="2be55-211">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-211">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="2be55-212">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-212">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="2be55-213">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-213">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="2be55-214">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-214">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="2be55-215">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-215">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="2be55-216">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="2be55-216">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="2be55-217">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-217">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="2be55-218">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="2be55-218">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="2be55-219">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-219">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="2be55-220">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-220">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="2be55-221">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-221">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="2be55-222">この例では、3つのフィールドをすべて受け取り、HWND やハンドルなどの win32 固有のデータ型を除外しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-222">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="2be55-223">注: sourceDevice は使用されますが、PointerDeviceRect と DisplayRect で sourceDevice の既存のユースケースをカバーすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2be55-223">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="2be55-224">また、point または rect のいずれかの場所が、webview の物理座標であることが想定されているという大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="2be55-224">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="2be55-225">つまり、webview と DPI のスケーリングが適用された相対的な座標です。</span><span class="sxs-lookup"><span data-stu-id="2be55-225">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="2be55-226">Members</span><span class="sxs-lookup"><span data-stu-id="2be55-226">Members</span></span>

#### <span data-ttu-id="2be55-227">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="2be55-227">get_ButtonChangeKind</span></span> 

<span data-ttu-id="2be55-228">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-228">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="2be55-229">パブリック HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="2be55-229">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="2be55-230">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-230">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="2be55-231">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-231">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-232">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="2be55-232">get_DisplayRect</span></span> 

<span data-ttu-id="2be55-233">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-233">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="2be55-234">パブリック HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayrect)</span><span class="sxs-lookup"><span data-stu-id="2be55-234">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="2be55-235">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="2be55-235">get_FrameId</span></span> 

<span data-ttu-id="2be55-236">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-236">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="2be55-237">パブリック HRESULT [get_FrameId](#get_frameid)(UINT32 \* フレーム id)</span><span class="sxs-lookup"><span data-stu-id="2be55-237">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="2be55-238">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-238">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-239">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-239">get_HimetricLocation</span></span> 

<span data-ttu-id="2be55-240">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-240">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="2be55-241">パブリック HRESULT [get_HimetricLocation](#get_himetriclocation)(ポイント \* himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="2be55-241">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="2be55-242">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-242">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-243">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-243">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="2be55-244">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-244">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="2be55-245">パブリック HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(ポイント \* himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="2be55-245">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="2be55-246">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-246">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-247">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="2be55-247">get_HistoryCount</span></span> 

<span data-ttu-id="2be55-248">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-248">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="2be55-249">パブリック HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="2be55-249">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="2be55-250">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-250">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-251">get_InputData</span><span class="sxs-lookup"><span data-stu-id="2be55-251">get_InputData</span></span> 

<span data-ttu-id="2be55-252">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-252">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="2be55-253">パブリック HRESULT [get_InputData](#get_inputdata)(INT32 \* inputdata)</span><span class="sxs-lookup"><span data-stu-id="2be55-253">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="2be55-254">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-254">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-255">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="2be55-255">get_KeyStates</span></span> 

<span data-ttu-id="2be55-256">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-256">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="2be55-257">パブリック HRESULT [get_KeyStates](#get_keystates)(DWORD \* keystates)</span><span class="sxs-lookup"><span data-stu-id="2be55-257">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="2be55-258">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-258">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-259">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-259">get_PenFlags</span></span> 

<span data-ttu-id="2be55-260">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-260">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="2be55-261">パブリック HRESULT [get_PenFlags](#get_penflags)(UINT32 \* ペンフラグ)</span><span class="sxs-lookup"><span data-stu-id="2be55-261">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="2be55-262">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-262">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="2be55-263">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-263">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-264">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="2be55-264">get_PenMask</span></span> 

<span data-ttu-id="2be55-265">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-265">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="2be55-266">パブリック HRESULT [get_PenMask](#get_penmask)(UINT32 \* ペンマスク)</span><span class="sxs-lookup"><span data-stu-id="2be55-266">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="2be55-267">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="2be55-267">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="2be55-268">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-268">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-269">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-269">get_PenPressure</span></span> 

<span data-ttu-id="2be55-270">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-270">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="2be55-271">パブリック HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* の筆圧)</span><span class="sxs-lookup"><span data-stu-id="2be55-271">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="2be55-272">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-272">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-273">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="2be55-273">get_PenRotation</span></span> 

<span data-ttu-id="2be55-274">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-274">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="2be55-275">パブリック HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* の回転回転)</span><span class="sxs-lookup"><span data-stu-id="2be55-275">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="2be55-276">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-276">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-277">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="2be55-277">get_PenTiltX</span></span> 

<span data-ttu-id="2be55-278">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-278">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="2be55-279">パブリック HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="2be55-279">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="2be55-280">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-280">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-281">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="2be55-281">get_PenTiltY</span></span> 

<span data-ttu-id="2be55-282">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-282">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="2be55-283">パブリック HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="2be55-283">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="2be55-284">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-284">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-285">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="2be55-285">get_PerformanceCount</span></span> 

<span data-ttu-id="2be55-286">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-286">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="2be55-287">パブリック HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="2be55-287">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="2be55-288">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-288">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-289">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-289">get_PixelLocation</span></span> 

<span data-ttu-id="2be55-290">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-290">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="2be55-291">パブリック HRESULT [get_PixelLocation](#get_pixellocation)(ポイント \* ピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="2be55-291">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="2be55-292">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-292">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-293">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-293">get_PixelLocationRaw</span></span> 

<span data-ttu-id="2be55-294">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-294">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="2be55-295">パブリック HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(ポイント \* ピクセルの場所 raw)</span><span class="sxs-lookup"><span data-stu-id="2be55-295">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="2be55-296">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-296">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-297">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="2be55-297">get_PointerDeviceRect</span></span> 

<span data-ttu-id="2be55-298">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-298">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="2be55-299">パブリック HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="2be55-299">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="2be55-300">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-300">get_PointerFlags</span></span> 

<span data-ttu-id="2be55-301">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-301">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="2be55-302">パブリック HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="2be55-302">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="2be55-303">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-303">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="2be55-304">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-304">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-305">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="2be55-305">get_PointerId</span></span> 

<span data-ttu-id="2be55-306">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-306">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="2be55-307">パブリック HRESULT [get_PointerId](#get_pointerid)(UINT32 \* ポインター id)</span><span class="sxs-lookup"><span data-stu-id="2be55-307">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="2be55-308">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-308">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-309">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="2be55-309">get_PointerKind</span></span> 

<span data-ttu-id="2be55-310">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-310">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="2be55-311">パブリック HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="2be55-311">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="2be55-312">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-312">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="2be55-313">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-313">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="2be55-314">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2be55-314">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="2be55-315">get_Time</span><span class="sxs-lookup"><span data-stu-id="2be55-315">get_Time</span></span> 

<span data-ttu-id="2be55-316">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-316">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="2be55-317">パブリック HRESULT [get_Time](#get_time)(DWORD \* 時刻)</span><span class="sxs-lookup"><span data-stu-id="2be55-317">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="2be55-318">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-318">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-319">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="2be55-319">get_TouchContact</span></span> 

<span data-ttu-id="2be55-320">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-320">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="2be55-321">パブリック HRESULT [get_TouchContact](#get_touchcontact)(RECT \* TouchContact)</span><span class="sxs-lookup"><span data-stu-id="2be55-321">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="2be55-322">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-322">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-323">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-323">get_TouchContactRaw</span></span> 

<span data-ttu-id="2be55-324">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-324">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="2be55-325">パブリック HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="2be55-325">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="2be55-326">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-326">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-327">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-327">get_TouchFlags</span></span> 

<span data-ttu-id="2be55-328">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-328">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="2be55-329">パブリック HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="2be55-329">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="2be55-330">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-330">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="2be55-331">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-331">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-332">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="2be55-332">get_TouchMask</span></span> 

<span data-ttu-id="2be55-333">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-333">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="2be55-334">パブリック HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* TouchMask)</span><span class="sxs-lookup"><span data-stu-id="2be55-334">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="2be55-335">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-335">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="2be55-336">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-336">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-337">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="2be55-337">get_TouchOrientation</span></span> 

<span data-ttu-id="2be55-338">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-338">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="2be55-339">パブリック HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="2be55-339">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="2be55-340">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-340">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-341">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-341">get_TouchPressure</span></span> 

<span data-ttu-id="2be55-342">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="2be55-342">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="2be55-343">パブリック HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="2be55-343">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="2be55-344">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-344">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-345">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="2be55-345">put_ButtonChangeKind</span></span> 

<span data-ttu-id="2be55-346">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-346">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="2be55-347">パブリック HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="2be55-347">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="2be55-348">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-348">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="2be55-349">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-349">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-350">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="2be55-350">put_DisplayRect</span></span> 

<span data-ttu-id="2be55-351">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-351">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="2be55-352">パブリック HRESULT [put_DisplayRect](#put_displayrect)(RECT displayrect)</span><span class="sxs-lookup"><span data-stu-id="2be55-352">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="2be55-353">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="2be55-353">put_FrameId</span></span> 

<span data-ttu-id="2be55-354">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-354">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="2be55-355">パブリック HRESULT [put_FrameId](#put_frameid)(UINT32 フレーム id)</span><span class="sxs-lookup"><span data-stu-id="2be55-355">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="2be55-356">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-356">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-357">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-357">put_HimetricLocation</span></span> 

<span data-ttu-id="2be55-358">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-358">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="2be55-359">パブリック HRESULT [put_HimetricLocation](#put_himetriclocation)(ポイント himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="2be55-359">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="2be55-360">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-360">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-361">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-361">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="2be55-362">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-362">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="2be55-363">パブリック HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(ポイント himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="2be55-363">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="2be55-364">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-364">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-365">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="2be55-365">put_HistoryCount</span></span> 

<span data-ttu-id="2be55-366">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-366">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="2be55-367">パブリック HRESULT [put_HistoryCount](#put_historycount)(UINT32 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="2be55-367">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="2be55-368">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-368">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-369">put_InputData</span><span class="sxs-lookup"><span data-stu-id="2be55-369">put_InputData</span></span> 

<span data-ttu-id="2be55-370">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-370">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="2be55-371">パブリック HRESULT [put_InputData](#put_inputdata)(INT32 inputdata)</span><span class="sxs-lookup"><span data-stu-id="2be55-371">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="2be55-372">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-372">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-373">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="2be55-373">put_KeyStates</span></span> 

<span data-ttu-id="2be55-374">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-374">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="2be55-375">パブリック HRESULT [put_KeyStates](#put_keystates)(DWORD keystates)</span><span class="sxs-lookup"><span data-stu-id="2be55-375">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="2be55-376">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-376">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-377">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-377">put_PenFlags</span></span> 

<span data-ttu-id="2be55-378">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-378">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="2be55-379">パブリック HRESULT [put_PenFlags](#put_penflags)(UINT32 のフラグ)</span><span class="sxs-lookup"><span data-stu-id="2be55-379">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="2be55-380">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-380">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="2be55-381">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-381">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-382">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="2be55-382">put_PenMask</span></span> 

<span data-ttu-id="2be55-383">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-383">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="2be55-384">パブリック HRESULT [put_PenMask](#put_penmask)(UINT32 のマスク)</span><span class="sxs-lookup"><span data-stu-id="2be55-384">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="2be55-385">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="2be55-385">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="2be55-386">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-386">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-387">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-387">put_PenPressure</span></span> 

<span data-ttu-id="2be55-388">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-388">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="2be55-389">パブリック HRESULT [put_PenPressure](#put_penpressure)(UINT32)</span><span class="sxs-lookup"><span data-stu-id="2be55-389">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="2be55-390">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-390">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-391">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="2be55-391">put_PenRotation</span></span> 

<span data-ttu-id="2be55-392">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-392">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="2be55-393">パブリック HRESULT [put_PenRotation](#put_penrotation)(UINT32 の回転)</span><span class="sxs-lookup"><span data-stu-id="2be55-393">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="2be55-394">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-394">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-395">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="2be55-395">put_PenTiltX</span></span> 

<span data-ttu-id="2be55-396">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-396">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="2be55-397">パブリック HRESULT [put_PenTiltX](#put_pentiltx)(INT32 PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="2be55-397">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="2be55-398">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-398">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-399">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="2be55-399">put_PenTiltY</span></span> 

<span data-ttu-id="2be55-400">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-400">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="2be55-401">パブリック HRESULT [put_PenTiltY](#put_pentilty)(INT32 PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="2be55-401">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="2be55-402">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-402">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-403">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="2be55-403">put_PerformanceCount</span></span> 

<span data-ttu-id="2be55-404">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-404">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="2be55-405">パブリック HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="2be55-405">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="2be55-406">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-406">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-407">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="2be55-407">put_PixelLocation</span></span> 

<span data-ttu-id="2be55-408">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-408">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="2be55-409">パブリック HRESULT [put_PixelLocation](#put_pixellocation)(ポイントピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="2be55-409">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="2be55-410">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-410">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-411">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-411">put_PixelLocationRaw</span></span> 

<span data-ttu-id="2be55-412">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-412">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="2be55-413">パブリック HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(ポイントのピクセルの位置に raw)</span><span class="sxs-lookup"><span data-stu-id="2be55-413">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="2be55-414">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-414">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-415">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="2be55-415">put_PointerDeviceRect</span></span> 

<span data-ttu-id="2be55-416">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-416">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="2be55-417">パブリック HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="2be55-417">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="2be55-418">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-418">put_PointerFlags</span></span> 

<span data-ttu-id="2be55-419">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-419">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="2be55-420">パブリック HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="2be55-420">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="2be55-421">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-421">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="2be55-422">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-422">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-423">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="2be55-423">put_PointerId</span></span> 

<span data-ttu-id="2be55-424">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-424">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="2be55-425">パブリック HRESULT [put_PointerId](#put_pointerid)(UINT32 ポインター id)</span><span class="sxs-lookup"><span data-stu-id="2be55-425">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="2be55-426">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-426">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-427">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="2be55-427">put_PointerKind</span></span> 

<span data-ttu-id="2be55-428">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-428">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="2be55-429">パブリック HRESULT [put_PointerKind](#put_pointerkind)(DWORD ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="2be55-429">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="2be55-430">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-430">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="2be55-431">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-431">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="2be55-432">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2be55-432">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="2be55-433">put_Time</span><span class="sxs-lookup"><span data-stu-id="2be55-433">put_Time</span></span> 

<span data-ttu-id="2be55-434">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-434">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="2be55-435">パブリック HRESULT [put_Time](#put_time)(DWORD 時刻)</span><span class="sxs-lookup"><span data-stu-id="2be55-435">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="2be55-436">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-436">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-437">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="2be55-437">put_TouchContact</span></span> 

<span data-ttu-id="2be55-438">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-438">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="2be55-439">パブリック HRESULT [put_TouchContact](#put_touchcontact)(RECT TouchContact)</span><span class="sxs-lookup"><span data-stu-id="2be55-439">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="2be55-440">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-440">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-441">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="2be55-441">put_TouchContactRaw</span></span> 

<span data-ttu-id="2be55-442">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-442">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="2be55-443">パブリック HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="2be55-443">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="2be55-444">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-444">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-445">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="2be55-445">put_TouchFlags</span></span> 

<span data-ttu-id="2be55-446">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-446">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="2be55-447">パブリック HRESULT [put_TouchFlags](#put_touchflags)(UINT32 TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="2be55-447">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="2be55-448">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-448">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="2be55-449">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-449">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-450">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="2be55-450">put_TouchMask</span></span> 

<span data-ttu-id="2be55-451">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-451">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="2be55-452">パブリック HRESULT [put_TouchMask](#put_touchmask)(UINT32 TouchMask)</span><span class="sxs-lookup"><span data-stu-id="2be55-452">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="2be55-453">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-453">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="2be55-454">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2be55-454">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-455">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="2be55-455">put_TouchOrientation</span></span> 

<span data-ttu-id="2be55-456">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-456">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="2be55-457">パブリック HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="2be55-457">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="2be55-458">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-458">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="2be55-459">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="2be55-459">put_TouchPressure</span></span> 

<span data-ttu-id="2be55-460">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="2be55-460">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="2be55-461">パブリック HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="2be55-461">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="2be55-462">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2be55-462">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

