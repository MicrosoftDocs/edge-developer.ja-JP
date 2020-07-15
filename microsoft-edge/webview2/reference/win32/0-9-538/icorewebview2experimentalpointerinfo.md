---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalPointerInfo
ms.openlocfilehash: b84c822e8b9e01d3b5a0e59baaeed5fc587d9a15
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879948"
---
# <span data-ttu-id="3ae57-104">インターフェイス ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="3ae57-104">interface ICoreWebView2ExperimentalPointerInfo</span></span> 

> [!NOTE]
> <span data-ttu-id="3ae57-105">これは、プレリリース SDK バージョン0.9.538 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="3ae57-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="3ae57-106">これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="3ae57-106">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="3ae57-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="3ae57-107">Summary</span></span>

 <span data-ttu-id="3ae57-108">Members</span><span class="sxs-lookup"><span data-stu-id="3ae57-108">Members</span></span>                        | <span data-ttu-id="3ae57-109">説明</span><span class="sxs-lookup"><span data-stu-id="3ae57-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3ae57-110">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-110">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="3ae57-111">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-111">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="3ae57-112">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-112">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="3ae57-113">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-113">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="3ae57-114">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="3ae57-114">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="3ae57-115">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-115">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="3ae57-116">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-116">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="3ae57-117">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-117">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-118">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-118">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="3ae57-119">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-119">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="3ae57-120">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-120">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="3ae57-121">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-121">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="3ae57-122">get_InputData</span><span class="sxs-lookup"><span data-stu-id="3ae57-122">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="3ae57-123">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-123">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="3ae57-124">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="3ae57-124">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="3ae57-125">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-125">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="3ae57-126">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-126">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="3ae57-127">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-127">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="3ae57-128">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-128">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="3ae57-129">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-129">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="3ae57-130">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-130">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="3ae57-131">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-131">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="3ae57-132">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="3ae57-132">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="3ae57-133">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-133">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-134">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="3ae57-134">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="3ae57-135">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-135">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="3ae57-136">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="3ae57-136">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="3ae57-137">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-137">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="3ae57-138">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-138">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="3ae57-139">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-139">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="3ae57-140">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-140">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="3ae57-141">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-141">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-142">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-142">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="3ae57-143">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-143">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="3ae57-144">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-144">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="3ae57-145">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-145">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="3ae57-146">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-146">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="3ae57-147">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-147">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="3ae57-148">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="3ae57-148">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="3ae57-149">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-149">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="3ae57-150">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-150">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="3ae57-151">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-151">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="3ae57-152">get_Time</span><span class="sxs-lookup"><span data-stu-id="3ae57-152">get_Time</span></span>](#get_time) | <span data-ttu-id="3ae57-153">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-153">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="3ae57-154">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="3ae57-154">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="3ae57-155">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-155">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="3ae57-156">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-156">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="3ae57-157">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-157">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="3ae57-158">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-158">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="3ae57-159">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-159">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="3ae57-160">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-160">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="3ae57-161">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-161">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="3ae57-162">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="3ae57-162">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="3ae57-163">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-163">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-164">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-164">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="3ae57-165">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-165">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="3ae57-166">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-166">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="3ae57-167">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-167">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="3ae57-168">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-168">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="3ae57-169">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-169">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="3ae57-170">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="3ae57-170">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="3ae57-171">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-171">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="3ae57-172">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-172">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="3ae57-173">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-173">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-174">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-174">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="3ae57-175">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-175">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="3ae57-176">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-176">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="3ae57-177">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-177">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="3ae57-178">put_InputData</span><span class="sxs-lookup"><span data-stu-id="3ae57-178">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="3ae57-179">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-179">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="3ae57-180">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="3ae57-180">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="3ae57-181">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-181">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="3ae57-182">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-182">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="3ae57-183">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-183">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="3ae57-184">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-184">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="3ae57-185">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-185">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="3ae57-186">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-186">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="3ae57-187">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-187">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="3ae57-188">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="3ae57-188">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="3ae57-189">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-189">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-190">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="3ae57-190">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="3ae57-191">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-191">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="3ae57-192">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="3ae57-192">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="3ae57-193">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-193">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="3ae57-194">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-194">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="3ae57-195">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-195">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="3ae57-196">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-196">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="3ae57-197">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-197">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-198">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-198">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="3ae57-199">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-199">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="3ae57-200">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-200">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="3ae57-201">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-201">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="3ae57-202">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-202">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="3ae57-203">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-203">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="3ae57-204">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="3ae57-204">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="3ae57-205">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-205">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="3ae57-206">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-206">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="3ae57-207">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-207">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="3ae57-208">put_Time</span><span class="sxs-lookup"><span data-stu-id="3ae57-208">put_Time</span></span>](#put_time) | <span data-ttu-id="3ae57-209">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-209">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="3ae57-210">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="3ae57-210">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="3ae57-211">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-211">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="3ae57-212">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-212">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="3ae57-213">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-213">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="3ae57-214">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-214">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="3ae57-215">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-215">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="3ae57-216">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-216">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="3ae57-217">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-217">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="3ae57-218">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="3ae57-218">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="3ae57-219">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-219">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="3ae57-220">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-220">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="3ae57-221">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-221">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="3ae57-222">この例では、3つのフィールドをすべて受け取り、HWND やハンドルなどの win32 固有のデータ型を除外しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-222">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="3ae57-223">注: sourceDevice は使用されますが、PointerDeviceRect と DisplayRect で sourceDevice の既存のユースケースをカバーすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-223">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="3ae57-224">また、point または rect のいずれかの場所が、webview の物理座標であることが想定されているという大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="3ae57-224">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="3ae57-225">つまり、webview と DPI のスケーリングが適用された相対的な座標です。</span><span class="sxs-lookup"><span data-stu-id="3ae57-225">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="3ae57-226">Members</span><span class="sxs-lookup"><span data-stu-id="3ae57-226">Members</span></span>

#### <span data-ttu-id="3ae57-227">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-227">get_ButtonChangeKind</span></span> 

<span data-ttu-id="3ae57-228">ポインターイベントの ButtonChangeKind を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-228">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="3ae57-229">パブリック HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="3ae57-229">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="3ae57-230">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-230">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="3ae57-231">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-231">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-232">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-232">get_DisplayRect</span></span> 

<span data-ttu-id="3ae57-233">Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-233">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="3ae57-234">パブリック HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayrect)</span><span class="sxs-lookup"><span data-stu-id="3ae57-234">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="3ae57-235">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="3ae57-235">get_FrameId</span></span> 

<span data-ttu-id="3ae57-236">ポインターイベントのフレーム Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-236">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="3ae57-237">パブリック HRESULT [get_FrameId](#get_frameid)(UINT32 \* フレーム id)</span><span class="sxs-lookup"><span data-stu-id="3ae57-237">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="3ae57-238">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-238">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-239">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-239">get_HimetricLocation</span></span> 

<span data-ttu-id="3ae57-240">ポインターイベントの HimetricLocation を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-240">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-241">パブリック HRESULT [get_HimetricLocation](#get_himetriclocation)(ポイント \* himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="3ae57-241">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="3ae57-242">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-242">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-243">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-243">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="3ae57-244">ポインターイベントの HimetricLocationRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-244">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="3ae57-245">パブリック HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(ポイント \* himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="3ae57-245">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="3ae57-246">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-246">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-247">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-247">get_HistoryCount</span></span> 

<span data-ttu-id="3ae57-248">ポインターイベントの履歴カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-248">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="3ae57-249">パブリック HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="3ae57-249">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="3ae57-250">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-250">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-251">get_InputData</span><span class="sxs-lookup"><span data-stu-id="3ae57-251">get_InputData</span></span> 

<span data-ttu-id="3ae57-252">ポインターイベントの InputData を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-252">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="3ae57-253">パブリック HRESULT [get_InputData](#get_inputdata)(INT32 \* inputdata)</span><span class="sxs-lookup"><span data-stu-id="3ae57-253">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="3ae57-254">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-254">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-255">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="3ae57-255">get_KeyStates</span></span> 

<span data-ttu-id="3ae57-256">ポインターイベントの KeyStates を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-256">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="3ae57-257">パブリック HRESULT [get_KeyStates](#get_keystates)(DWORD \* keystates)</span><span class="sxs-lookup"><span data-stu-id="3ae57-257">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="3ae57-258">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-258">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-259">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-259">get_PenFlags</span></span> 

<span data-ttu-id="3ae57-260">ポインターイベントのペンフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-260">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="3ae57-261">パブリック HRESULT [get_PenFlags](#get_penflags)(UINT32 \* ペンフラグ)</span><span class="sxs-lookup"><span data-stu-id="3ae57-261">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="3ae57-262">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-262">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="3ae57-263">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-263">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-264">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-264">get_PenMask</span></span> 

<span data-ttu-id="3ae57-265">ポインターイベントのペンマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-265">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="3ae57-266">パブリック HRESULT [get_PenMask](#get_penmask)(UINT32 \* ペンマスク)</span><span class="sxs-lookup"><span data-stu-id="3ae57-266">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="3ae57-267">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-267">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="3ae57-268">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-268">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-269">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-269">get_PenPressure</span></span> 

<span data-ttu-id="3ae57-270">ポインターイベントの筆圧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-270">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="3ae57-271">パブリック HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* の筆圧)</span><span class="sxs-lookup"><span data-stu-id="3ae57-271">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="3ae57-272">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-272">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-273">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="3ae57-273">get_PenRotation</span></span> 

<span data-ttu-id="3ae57-274">ポインターイベントのペン回転を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-274">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-275">パブリック HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* の回転回転)</span><span class="sxs-lookup"><span data-stu-id="3ae57-275">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="3ae57-276">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-276">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-277">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="3ae57-277">get_PenTiltX</span></span> 

<span data-ttu-id="3ae57-278">ポインターイベントの PenTiltX を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-278">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="3ae57-279">パブリック HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="3ae57-279">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="3ae57-280">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-280">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-281">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="3ae57-281">get_PenTiltY</span></span> 

<span data-ttu-id="3ae57-282">ポインターイベントの PenTiltY を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-282">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="3ae57-283">パブリック HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="3ae57-283">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="3ae57-284">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-284">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-285">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-285">get_PerformanceCount</span></span> 

<span data-ttu-id="3ae57-286">ポインターイベントの PerformanceCount を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-286">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="3ae57-287">パブリック HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="3ae57-287">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="3ae57-288">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-288">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-289">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-289">get_PixelLocation</span></span> 

<span data-ttu-id="3ae57-290">ポインターイベントのピクセルの位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-290">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-291">パブリック HRESULT [get_PixelLocation](#get_pixellocation)(ポイント \* ピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="3ae57-291">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="3ae57-292">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-292">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-293">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-293">get_PixelLocationRaw</span></span> 

<span data-ttu-id="3ae57-294">ポインターイベントのピクセルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-294">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="3ae57-295">パブリック HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(ポイント \* ピクセルの場所 raw)</span><span class="sxs-lookup"><span data-stu-id="3ae57-295">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="3ae57-296">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-296">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-297">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-297">get_PointerDeviceRect</span></span> 

<span data-ttu-id="3ae57-298">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-298">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="3ae57-299">パブリック HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="3ae57-299">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="3ae57-300">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-300">get_PointerFlags</span></span> 

<span data-ttu-id="3ae57-301">ポインターイベントの PointerFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-301">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="3ae57-302">パブリック HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="3ae57-302">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="3ae57-303">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-303">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="3ae57-304">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-304">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-305">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="3ae57-305">get_PointerId</span></span> 

<span data-ttu-id="3ae57-306">ポインターイベントのポインタ Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-306">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="3ae57-307">パブリック HRESULT [get_PointerId](#get_pointerid)(UINT32 \* ポインター id)</span><span class="sxs-lookup"><span data-stu-id="3ae57-307">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="3ae57-308">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-308">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-309">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-309">get_PointerKind</span></span> 

<span data-ttu-id="3ae57-310">ポインターイベントのポインターの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-310">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="3ae57-311">パブリック HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="3ae57-311">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="3ae57-312">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-312">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="3ae57-313">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-313">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="3ae57-314">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3ae57-314">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="3ae57-315">get_Time</span><span class="sxs-lookup"><span data-stu-id="3ae57-315">get_Time</span></span> 

<span data-ttu-id="3ae57-316">ポインターイベントの時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-316">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="3ae57-317">パブリック HRESULT [get_Time](#get_time)(DWORD \* 時刻)</span><span class="sxs-lookup"><span data-stu-id="3ae57-317">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="3ae57-318">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-318">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-319">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="3ae57-319">get_TouchContact</span></span> 

<span data-ttu-id="3ae57-320">ポインターイベントの TouchContact を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-320">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="3ae57-321">パブリック HRESULT [get_TouchContact](#get_touchcontact)(RECT \* TouchContact)</span><span class="sxs-lookup"><span data-stu-id="3ae57-321">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="3ae57-322">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-322">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-323">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-323">get_TouchContactRaw</span></span> 

<span data-ttu-id="3ae57-324">ポインターイベントの TouchContactRaw を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-324">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="3ae57-325">パブリック HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="3ae57-325">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="3ae57-326">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-326">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-327">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-327">get_TouchFlags</span></span> 

<span data-ttu-id="3ae57-328">ポインターイベントの TouchFlags を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-328">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="3ae57-329">パブリック HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="3ae57-329">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="3ae57-330">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-330">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="3ae57-331">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-331">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-332">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-332">get_TouchMask</span></span> 

<span data-ttu-id="3ae57-333">ポインターイベントの TouchMask を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-333">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="3ae57-334">パブリック HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* TouchMask)</span><span class="sxs-lookup"><span data-stu-id="3ae57-334">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="3ae57-335">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-335">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="3ae57-336">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-336">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-337">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="3ae57-337">get_TouchOrientation</span></span> 

<span data-ttu-id="3ae57-338">ポインターイベントの TouchOrientation を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-338">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-339">パブリック HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="3ae57-339">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="3ae57-340">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-340">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-341">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-341">get_TouchPressure</span></span> 

<span data-ttu-id="3ae57-342">ポインターイベントの TouchPressure を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-342">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="3ae57-343">パブリック HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="3ae57-343">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="3ae57-344">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-344">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-345">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-345">put_ButtonChangeKind</span></span> 

<span data-ttu-id="3ae57-346">ポインターイベントの ButtonChangeKind を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-346">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="3ae57-347">パブリック HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span><span class="sxs-lookup"><span data-stu-id="3ae57-347">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="3ae57-348">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-348">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="3ae57-349">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-349">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-350">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-350">put_DisplayRect</span></span> 

<span data-ttu-id="3ae57-351">Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-351">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="3ae57-352">パブリック HRESULT [put_DisplayRect](#put_displayrect)(RECT displayrect)</span><span class="sxs-lookup"><span data-stu-id="3ae57-352">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="3ae57-353">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="3ae57-353">put_FrameId</span></span> 

<span data-ttu-id="3ae57-354">ポインターイベントのフレーム Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-354">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="3ae57-355">パブリック HRESULT [put_FrameId](#put_frameid)(UINT32 フレーム id)</span><span class="sxs-lookup"><span data-stu-id="3ae57-355">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="3ae57-356">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-356">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-357">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-357">put_HimetricLocation</span></span> 

<span data-ttu-id="3ae57-358">ポインターイベントの HimetricLocation を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-358">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-359">パブリック HRESULT [put_HimetricLocation](#put_himetriclocation)(ポイント himetricLocation)</span><span class="sxs-lookup"><span data-stu-id="3ae57-359">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="3ae57-360">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-360">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-361">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-361">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="3ae57-362">ポインターイベントの HimetricLocationRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-362">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="3ae57-363">パブリック HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(ポイント himetricLocationRaw)</span><span class="sxs-lookup"><span data-stu-id="3ae57-363">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="3ae57-364">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-364">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-365">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-365">put_HistoryCount</span></span> 

<span data-ttu-id="3ae57-366">ポインターイベントの履歴カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-366">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="3ae57-367">パブリック HRESULT [put_HistoryCount](#put_historycount)(UINT32 履歴カウント)</span><span class="sxs-lookup"><span data-stu-id="3ae57-367">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="3ae57-368">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-368">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-369">put_InputData</span><span class="sxs-lookup"><span data-stu-id="3ae57-369">put_InputData</span></span> 

<span data-ttu-id="3ae57-370">ポインターイベントの InputData を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-370">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="3ae57-371">パブリック HRESULT [put_InputData](#put_inputdata)(INT32 inputdata)</span><span class="sxs-lookup"><span data-stu-id="3ae57-371">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="3ae57-372">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-372">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-373">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="3ae57-373">put_KeyStates</span></span> 

<span data-ttu-id="3ae57-374">ポインターイベントの KeyStates を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-374">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="3ae57-375">パブリック HRESULT [put_KeyStates](#put_keystates)(DWORD keystates)</span><span class="sxs-lookup"><span data-stu-id="3ae57-375">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="3ae57-376">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-376">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-377">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-377">put_PenFlags</span></span> 

<span data-ttu-id="3ae57-378">ポインターイベントのペンフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-378">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="3ae57-379">パブリック HRESULT [put_PenFlags](#put_penflags)(UINT32 のフラグ)</span><span class="sxs-lookup"><span data-stu-id="3ae57-379">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="3ae57-380">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-380">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="3ae57-381">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-381">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-382">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-382">put_PenMask</span></span> 

<span data-ttu-id="3ae57-383">ポインターイベントの "ペンマスク" を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-383">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="3ae57-384">パブリック HRESULT [put_PenMask](#put_penmask)(UINT32 のマスク)</span><span class="sxs-lookup"><span data-stu-id="3ae57-384">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="3ae57-385">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-385">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="3ae57-386">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-386">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-387">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-387">put_PenPressure</span></span> 

<span data-ttu-id="3ae57-388">ポインターイベントの "ペンの筆圧" を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-388">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="3ae57-389">パブリック HRESULT [put_PenPressure](#put_penpressure)(UINT32)</span><span class="sxs-lookup"><span data-stu-id="3ae57-389">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="3ae57-390">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-390">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-391">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="3ae57-391">put_PenRotation</span></span> 

<span data-ttu-id="3ae57-392">ポインターイベントのペン回転を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-392">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-393">パブリック HRESULT [put_PenRotation](#put_penrotation)(UINT32 の回転)</span><span class="sxs-lookup"><span data-stu-id="3ae57-393">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="3ae57-394">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-394">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-395">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="3ae57-395">put_PenTiltX</span></span> 

<span data-ttu-id="3ae57-396">ポインターイベントの PenTiltX を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-396">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="3ae57-397">パブリック HRESULT [put_PenTiltX](#put_pentiltx)(INT32 PenTiltX)</span><span class="sxs-lookup"><span data-stu-id="3ae57-397">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="3ae57-398">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-398">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-399">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="3ae57-399">put_PenTiltY</span></span> 

<span data-ttu-id="3ae57-400">ポインターイベントの PenTiltY を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-400">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="3ae57-401">パブリック HRESULT [put_PenTiltY](#put_pentilty)(INT32 PenTiltY)</span><span class="sxs-lookup"><span data-stu-id="3ae57-401">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="3ae57-402">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-402">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-403">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="3ae57-403">put_PerformanceCount</span></span> 

<span data-ttu-id="3ae57-404">ポインターイベントの PerformanceCount を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-404">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="3ae57-405">パブリック HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 PerformanceCount)</span><span class="sxs-lookup"><span data-stu-id="3ae57-405">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="3ae57-406">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-406">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-407">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="3ae57-407">put_PixelLocation</span></span> 

<span data-ttu-id="3ae57-408">ポインターイベントのピクセルの位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-408">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-409">パブリック HRESULT [put_PixelLocation](#put_pixellocation)(ポイントピクセルの場所)</span><span class="sxs-lookup"><span data-stu-id="3ae57-409">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="3ae57-410">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-410">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-411">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-411">put_PixelLocationRaw</span></span> 

<span data-ttu-id="3ae57-412">ポインターイベントのピクセルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-412">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="3ae57-413">パブリック HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(ポイントのピクセルの位置に raw)</span><span class="sxs-lookup"><span data-stu-id="3ae57-413">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="3ae57-414">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-414">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-415">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="3ae57-415">put_PointerDeviceRect</span></span> 

<span data-ttu-id="3ae57-416">Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-416">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="3ae57-417">パブリック HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT PointerDeviceRect)</span><span class="sxs-lookup"><span data-stu-id="3ae57-417">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="3ae57-418">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-418">put_PointerFlags</span></span> 

<span data-ttu-id="3ae57-419">ポインターイベントの PointerFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-419">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="3ae57-420">パブリック HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 PointerFlags)</span><span class="sxs-lookup"><span data-stu-id="3ae57-420">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="3ae57-421">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-421">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="3ae57-422">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-422">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-423">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="3ae57-423">put_PointerId</span></span> 

<span data-ttu-id="3ae57-424">ポインターイベントのポインタ Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-424">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="3ae57-425">パブリック HRESULT [put_PointerId](#put_pointerid)(UINT32 ポインター id)</span><span class="sxs-lookup"><span data-stu-id="3ae57-425">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="3ae57-426">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-426">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-427">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="3ae57-427">put_PointerKind</span></span> 

<span data-ttu-id="3ae57-428">ポインターイベントのポインターの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-428">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="3ae57-429">パブリック HRESULT [put_PointerKind](#put_pointerkind)(DWORD ポインター kind)</span><span class="sxs-lookup"><span data-stu-id="3ae57-429">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="3ae57-430">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-430">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="3ae57-431">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-431">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="3ae57-432">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3ae57-432">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="3ae57-433">put_Time</span><span class="sxs-lookup"><span data-stu-id="3ae57-433">put_Time</span></span> 

<span data-ttu-id="3ae57-434">ポインターイベントの時刻を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-434">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="3ae57-435">パブリック HRESULT [put_Time](#put_time)(DWORD 時刻)</span><span class="sxs-lookup"><span data-stu-id="3ae57-435">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="3ae57-436">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-436">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-437">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="3ae57-437">put_TouchContact</span></span> 

<span data-ttu-id="3ae57-438">ポインターイベントの TouchContact を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-438">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="3ae57-439">パブリック HRESULT [put_TouchContact](#put_touchcontact)(RECT TouchContact)</span><span class="sxs-lookup"><span data-stu-id="3ae57-439">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="3ae57-440">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-440">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-441">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="3ae57-441">put_TouchContactRaw</span></span> 

<span data-ttu-id="3ae57-442">ポインターイベントの TouchContactRaw を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-442">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="3ae57-443">パブリック HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT TouchContactRaw)</span><span class="sxs-lookup"><span data-stu-id="3ae57-443">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="3ae57-444">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-444">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-445">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="3ae57-445">put_TouchFlags</span></span> 

<span data-ttu-id="3ae57-446">ポインターイベントの TouchFlags を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-446">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="3ae57-447">パブリック HRESULT [put_TouchFlags](#put_touchflags)(UINT32 TouchFlags)</span><span class="sxs-lookup"><span data-stu-id="3ae57-447">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="3ae57-448">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-448">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="3ae57-449">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-449">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-450">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="3ae57-450">put_TouchMask</span></span> 

<span data-ttu-id="3ae57-451">ポインターイベントの TouchMask を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-451">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="3ae57-452">パブリック HRESULT [put_TouchMask](#put_touchmask)(UINT32 TouchMask)</span><span class="sxs-lookup"><span data-stu-id="3ae57-452">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="3ae57-453">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-453">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="3ae57-454">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae57-454">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-455">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="3ae57-455">put_TouchOrientation</span></span> 

<span data-ttu-id="3ae57-456">ポインターイベントの TouchOrientation を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-456">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="3ae57-457">パブリック HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 TouchOrientation)</span><span class="sxs-lookup"><span data-stu-id="3ae57-457">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="3ae57-458">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-458">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="3ae57-459">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="3ae57-459">put_TouchPressure</span></span> 

<span data-ttu-id="3ae57-460">ポインターイベントの TouchPressure を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ae57-460">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="3ae57-461">パブリック HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 TouchPressure)</span><span class="sxs-lookup"><span data-stu-id="3ae57-461">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="3ae57-462">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="3ae57-462">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

