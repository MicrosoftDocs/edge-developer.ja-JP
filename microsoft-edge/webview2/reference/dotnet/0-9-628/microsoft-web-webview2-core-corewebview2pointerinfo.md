---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2PointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PointerInfo。
ms.openlocfilehash: 34ffa5fe0eabfe8e822db2792d2b25ab5106442a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012251"
---
# <span data-ttu-id="de36b-104">WebView2 クラス (CoreWebView2PointerInfo クラス)</span><span class="sxs-lookup"><span data-stu-id="de36b-104">Microsoft.Web.WebView2.Core.CoreWebView2PointerInfo class</span></span> 

<span data-ttu-id="de36b-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="de36b-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="de36b-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="de36b-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="de36b-107">これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="de36b-107">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="de36b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="de36b-108">Summary</span></span>

 <span data-ttu-id="de36b-109">Members</span><span class="sxs-lookup"><span data-stu-id="de36b-109">Members</span></span>                        | <span data-ttu-id="de36b-110">説明</span><span class="sxs-lookup"><span data-stu-id="de36b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="de36b-111">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="de36b-111">ButtonChangeKind</span></span>](#buttonchangekind) | <span data-ttu-id="de36b-112">ポインターイベントの ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="de36b-112">The ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="de36b-113">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="de36b-113">DisplayRect</span></span>](#displayrect) | <span data-ttu-id="de36b-114">Windows SDK (winuser) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="de36b-114">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="de36b-115">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="de36b-115">FrameId</span></span>](#frameid) | <span data-ttu-id="de36b-116">ポインターイベントのフレーム Id。</span><span class="sxs-lookup"><span data-stu-id="de36b-116">The FrameID of the pointer event.</span></span>
[<span data-ttu-id="de36b-117">場所の HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="de36b-117">HimetricLocation</span></span>](#himetriclocation) | <span data-ttu-id="de36b-118">ポインターイベントの HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="de36b-118">The HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="de36b-119">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="de36b-119">HimetricLocationRaw</span></span>](#himetriclocationraw) | <span data-ttu-id="de36b-120">ポインターイベントのロウ Metriclocation。</span><span class="sxs-lookup"><span data-stu-id="de36b-120">The HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="de36b-121">履歴カウント</span><span class="sxs-lookup"><span data-stu-id="de36b-121">HistoryCount</span></span>](#historycount) | <span data-ttu-id="de36b-122">ポインターイベントの履歴カウント。</span><span class="sxs-lookup"><span data-stu-id="de36b-122">The HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="de36b-123">InputData</span><span class="sxs-lookup"><span data-stu-id="de36b-123">InputData</span></span>](#inputdata) | <span data-ttu-id="de36b-124">ポインターイベントの InputData。</span><span class="sxs-lookup"><span data-stu-id="de36b-124">The InputData of the pointer event.</span></span>
[<span data-ttu-id="de36b-125">KeyStates</span><span class="sxs-lookup"><span data-stu-id="de36b-125">KeyStates</span></span>](#keystates) | <span data-ttu-id="de36b-126">ポインターイベントの KeyStates。</span><span class="sxs-lookup"><span data-stu-id="de36b-126">The KeyStates of the pointer event.</span></span>
[<span data-ttu-id="de36b-127">ペンフラグ</span><span class="sxs-lookup"><span data-stu-id="de36b-127">PenFlags</span></span>](#penflags) | <span data-ttu-id="de36b-128">ポインターイベントのペンフラグ。</span><span class="sxs-lookup"><span data-stu-id="de36b-128">The PenFlags of the pointer event.</span></span>
[<span data-ttu-id="de36b-129">ペンマスク</span><span class="sxs-lookup"><span data-stu-id="de36b-129">PenMask</span></span>](#penmask) | <span data-ttu-id="de36b-130">ポインターイベントのペンマスク。</span><span class="sxs-lookup"><span data-stu-id="de36b-130">The PenMask of the pointer event.</span></span>
[<span data-ttu-id="de36b-131">ペンの筆圧</span><span class="sxs-lookup"><span data-stu-id="de36b-131">PenPressure</span></span>](#penpressure) | <span data-ttu-id="de36b-132">ポインターイベントのペンの筆圧。</span><span class="sxs-lookup"><span data-stu-id="de36b-132">The PenPressure of the pointer event.</span></span>
[<span data-ttu-id="de36b-133">ペンの回転</span><span class="sxs-lookup"><span data-stu-id="de36b-133">PenRotation</span></span>](#penrotation) | <span data-ttu-id="de36b-134">ポインターイベントのペン回転。</span><span class="sxs-lookup"><span data-stu-id="de36b-134">The PenRotation of the pointer event.</span></span>
[<span data-ttu-id="de36b-135">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="de36b-135">PenTiltX</span></span>](#pentiltx) | <span data-ttu-id="de36b-136">ポインターイベントの PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="de36b-136">The PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="de36b-137">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="de36b-137">PenTiltY</span></span>](#pentilty) | <span data-ttu-id="de36b-138">ポインターイベントの PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="de36b-138">The PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="de36b-139">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="de36b-139">PerformanceCount</span></span>](#performancecount) | <span data-ttu-id="de36b-140">ポインターイベントの PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="de36b-140">The PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="de36b-141">ピクセルの位置</span><span class="sxs-lookup"><span data-stu-id="de36b-141">PixelLocation</span></span>](#pixellocation) | <span data-ttu-id="de36b-142">ポインターイベントのピクセルの位置。</span><span class="sxs-lookup"><span data-stu-id="de36b-142">The PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="de36b-143">ピクセルの場所 Raw</span><span class="sxs-lookup"><span data-stu-id="de36b-143">PixelLocationRaw</span></span>](#pixellocationraw) | <span data-ttu-id="de36b-144">ポインターイベントのピクセルの場所。</span><span class="sxs-lookup"><span data-stu-id="de36b-144">The PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="de36b-145">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="de36b-145">PointerDeviceRect</span></span>](#pointerdevicerect) | <span data-ttu-id="de36b-146">Windows SDK で定義されている POINTER_INFO 構造体の sourceDevice プロパティの PointerDeviceRect です (winuser. h)。</span><span class="sxs-lookup"><span data-stu-id="de36b-146">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="de36b-147">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="de36b-147">PointerFlags</span></span>](#pointerflags) | <span data-ttu-id="de36b-148">ポインターイベントの PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="de36b-148">The PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="de36b-149">ポインター Id</span><span class="sxs-lookup"><span data-stu-id="de36b-149">PointerId</span></span>](#pointerid) | <span data-ttu-id="de36b-150">ポインターイベントのポインタ Id。</span><span class="sxs-lookup"><span data-stu-id="de36b-150">The PointerId of the pointer event.</span></span>
[<span data-ttu-id="de36b-151">ポインターの種類</span><span class="sxs-lookup"><span data-stu-id="de36b-151">PointerKind</span></span>](#pointerkind) | <span data-ttu-id="de36b-152">ポインターイベントのポインターの種類。</span><span class="sxs-lookup"><span data-stu-id="de36b-152">The PointerKind of the pointer event.</span></span>
[<span data-ttu-id="de36b-153">時間</span><span class="sxs-lookup"><span data-stu-id="de36b-153">Time</span></span>](#time) | <span data-ttu-id="de36b-154">ポインターイベントの時刻。</span><span class="sxs-lookup"><span data-stu-id="de36b-154">The Time of the pointer event.</span></span>
[<span data-ttu-id="de36b-155">TouchContact</span><span class="sxs-lookup"><span data-stu-id="de36b-155">TouchContact</span></span>](#touchcontact) | <span data-ttu-id="de36b-156">ポインターイベントの TouchContact。</span><span class="sxs-lookup"><span data-stu-id="de36b-156">The TouchContact of the pointer event.</span></span>
[<span data-ttu-id="de36b-157">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="de36b-157">TouchContactRaw</span></span>](#touchcontactraw) | <span data-ttu-id="de36b-158">ポインターイベントの TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="de36b-158">The TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="de36b-159">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="de36b-159">TouchFlags</span></span>](#touchflags) | <span data-ttu-id="de36b-160">ポインターイベントの TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="de36b-160">The TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="de36b-161">TouchMask</span><span class="sxs-lookup"><span data-stu-id="de36b-161">TouchMask</span></span>](#touchmask) | <span data-ttu-id="de36b-162">ポインターイベントの TouchMask。</span><span class="sxs-lookup"><span data-stu-id="de36b-162">The TouchMask of the pointer event.</span></span>
[<span data-ttu-id="de36b-163">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="de36b-163">TouchOrientation</span></span>](#touchorientation) | <span data-ttu-id="de36b-164">ポインターイベントの TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="de36b-164">The TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="de36b-165">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="de36b-165">TouchPressure</span></span>](#touchpressure) | <span data-ttu-id="de36b-166">ポインターイベントの TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="de36b-166">The TouchPressure of the pointer event.</span></span>

## <span data-ttu-id="de36b-167">Members</span><span class="sxs-lookup"><span data-stu-id="de36b-167">Members</span></span>

#### <span data-ttu-id="de36b-168">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="de36b-168">ButtonChangeKind</span></span> 

<span data-ttu-id="de36b-169">ポインターイベントの ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="de36b-169">The ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="de36b-170">パブリック int [ボタンの Changekind](#buttonchangekind)</span><span class="sxs-lookup"><span data-stu-id="de36b-170">public int [ButtonChangeKind](#buttonchangekind)</span></span>

<span data-ttu-id="de36b-171">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-171">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="de36b-172">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="de36b-172">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-173">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="de36b-173">DisplayRect</span></span> 

<span data-ttu-id="de36b-174">Windows SDK (winuser) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="de36b-174">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="de36b-175">パブリック四角形の [Displayrect](#displayrect)</span><span class="sxs-lookup"><span data-stu-id="de36b-175">public Rectangle [DisplayRect](#displayrect)</span></span>

#### <span data-ttu-id="de36b-176">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="de36b-176">FrameId</span></span> 

<span data-ttu-id="de36b-177">ポインターイベントのフレーム Id。</span><span class="sxs-lookup"><span data-stu-id="de36b-177">The FrameID of the pointer event.</span></span>

> <span data-ttu-id="de36b-178">パブリック uint [フレーム id](#frameid)</span><span class="sxs-lookup"><span data-stu-id="de36b-178">public uint [FrameId](#frameid)</span></span>

<span data-ttu-id="de36b-179">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-179">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-180">場所の HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="de36b-180">HimetricLocation</span></span> 

<span data-ttu-id="de36b-181">ポインターイベントの HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="de36b-181">The HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="de36b-182">パブリックポイントの [Himetriclocation](#himetriclocation)</span><span class="sxs-lookup"><span data-stu-id="de36b-182">public Point [HimetricLocation](#himetriclocation)</span></span>

<span data-ttu-id="de36b-183">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-183">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-184">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="de36b-184">HimetricLocationRaw</span></span> 

<span data-ttu-id="de36b-185">ポインターイベントのロウ Metriclocation。</span><span class="sxs-lookup"><span data-stu-id="de36b-185">The HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="de36b-186">パブリックポイントの [Himetriclocationraw](#himetriclocationraw)</span><span class="sxs-lookup"><span data-stu-id="de36b-186">public Point [HimetricLocationRaw](#himetriclocationraw)</span></span>

<span data-ttu-id="de36b-187">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-187">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-188">履歴カウント</span><span class="sxs-lookup"><span data-stu-id="de36b-188">HistoryCount</span></span> 

<span data-ttu-id="de36b-189">ポインターイベントの履歴カウント。</span><span class="sxs-lookup"><span data-stu-id="de36b-189">The HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="de36b-190">パブリック uint [履歴カウント](#historycount)</span><span class="sxs-lookup"><span data-stu-id="de36b-190">public uint [HistoryCount](#historycount)</span></span>

<span data-ttu-id="de36b-191">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-191">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-192">InputData</span><span class="sxs-lookup"><span data-stu-id="de36b-192">InputData</span></span> 

<span data-ttu-id="de36b-193">ポインターイベントの InputData。</span><span class="sxs-lookup"><span data-stu-id="de36b-193">The InputData of the pointer event.</span></span>

> <span data-ttu-id="de36b-194">パブリック int の [Inputdata](#inputdata)</span><span class="sxs-lookup"><span data-stu-id="de36b-194">public int [InputData](#inputdata)</span></span>

<span data-ttu-id="de36b-195">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-195">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-196">KeyStates</span><span class="sxs-lookup"><span data-stu-id="de36b-196">KeyStates</span></span> 

<span data-ttu-id="de36b-197">ポインターイベントの KeyStates。</span><span class="sxs-lookup"><span data-stu-id="de36b-197">The KeyStates of the pointer event.</span></span>

> <span data-ttu-id="de36b-198">パブリック uint [Keystates](#keystates)</span><span class="sxs-lookup"><span data-stu-id="de36b-198">public uint [KeyStates](#keystates)</span></span>

<span data-ttu-id="de36b-199">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-199">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-200">ペンフラグ</span><span class="sxs-lookup"><span data-stu-id="de36b-200">PenFlags</span></span> 

<span data-ttu-id="de36b-201">ポインターイベントのペンフラグ。</span><span class="sxs-lookup"><span data-stu-id="de36b-201">The PenFlags of the pointer event.</span></span>

> <span data-ttu-id="de36b-202">パブリック uint の [フラグ](#penflags)</span><span class="sxs-lookup"><span data-stu-id="de36b-202">public uint [PenFlags](#penflags)</span></span>

<span data-ttu-id="de36b-203">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-203">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="de36b-204">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="de36b-204">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-205">ペンマスク</span><span class="sxs-lookup"><span data-stu-id="de36b-205">PenMask</span></span> 

<span data-ttu-id="de36b-206">ポインターイベントのペンマスク。</span><span class="sxs-lookup"><span data-stu-id="de36b-206">The PenMask of the pointer event.</span></span>

> <span data-ttu-id="de36b-207">パブリック uint の [マスク](#penmask)</span><span class="sxs-lookup"><span data-stu-id="de36b-207">public uint [PenMask](#penmask)</span></span>

<span data-ttu-id="de36b-208">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="de36b-208">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="de36b-209">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="de36b-209">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-210">ペンの筆圧</span><span class="sxs-lookup"><span data-stu-id="de36b-210">PenPressure</span></span> 

<span data-ttu-id="de36b-211">ポインターイベントのペンの筆圧。</span><span class="sxs-lookup"><span data-stu-id="de36b-211">The PenPressure of the pointer event.</span></span>

> <span data-ttu-id="de36b-212">公開 uint の [気圧](#penpressure)</span><span class="sxs-lookup"><span data-stu-id="de36b-212">public uint [PenPressure](#penpressure)</span></span>

<span data-ttu-id="de36b-213">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-213">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-214">ペンの回転</span><span class="sxs-lookup"><span data-stu-id="de36b-214">PenRotation</span></span> 

<span data-ttu-id="de36b-215">ポインターイベントのペン回転。</span><span class="sxs-lookup"><span data-stu-id="de36b-215">The PenRotation of the pointer event.</span></span>

> <span data-ttu-id="de36b-216">公開 uint の [回転](#penrotation)</span><span class="sxs-lookup"><span data-stu-id="de36b-216">public uint [PenRotation](#penrotation)</span></span>

<span data-ttu-id="de36b-217">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-217">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-218">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="de36b-218">PenTiltX</span></span> 

<span data-ttu-id="de36b-219">ポインターイベントの PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="de36b-219">The PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="de36b-220">パブリック int [PenTiltX](#pentiltx)</span><span class="sxs-lookup"><span data-stu-id="de36b-220">public int [PenTiltX](#pentiltx)</span></span>

<span data-ttu-id="de36b-221">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-221">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-222">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="de36b-222">PenTiltY</span></span> 

<span data-ttu-id="de36b-223">ポインターイベントの PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="de36b-223">The PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="de36b-224">パブリック int [PenTiltY](#pentilty)</span><span class="sxs-lookup"><span data-stu-id="de36b-224">public int [PenTiltY](#pentilty)</span></span>

<span data-ttu-id="de36b-225">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-225">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-226">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="de36b-226">PerformanceCount</span></span> 

<span data-ttu-id="de36b-227">ポインターイベントの PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="de36b-227">The PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="de36b-228">パブリック ulong [PerformanceCount](#performancecount)</span><span class="sxs-lookup"><span data-stu-id="de36b-228">public ulong [PerformanceCount](#performancecount)</span></span>

<span data-ttu-id="de36b-229">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-229">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-230">ピクセルの位置</span><span class="sxs-lookup"><span data-stu-id="de36b-230">PixelLocation</span></span> 

<span data-ttu-id="de36b-231">ポインターイベントのピクセルの位置。</span><span class="sxs-lookup"><span data-stu-id="de36b-231">The PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="de36b-232">パブリックポイントの [ピクセルの位置](#pixellocation)</span><span class="sxs-lookup"><span data-stu-id="de36b-232">public Point [PixelLocation](#pixellocation)</span></span>

<span data-ttu-id="de36b-233">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-233">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-234">ピクセルの場所 Raw</span><span class="sxs-lookup"><span data-stu-id="de36b-234">PixelLocationRaw</span></span> 

<span data-ttu-id="de36b-235">ポインターイベントのピクセルの場所。</span><span class="sxs-lookup"><span data-stu-id="de36b-235">The PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="de36b-236">パブリックポイントのピクセルの位置の [raw](#pixellocationraw)</span><span class="sxs-lookup"><span data-stu-id="de36b-236">public Point [PixelLocationRaw](#pixellocationraw)</span></span>

<span data-ttu-id="de36b-237">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-237">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-238">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="de36b-238">PointerDeviceRect</span></span> 

<span data-ttu-id="de36b-239">Windows SDK で定義されている POINTER_INFO 構造体の sourceDevice プロパティの PointerDeviceRect です (winuser. h)。</span><span class="sxs-lookup"><span data-stu-id="de36b-239">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="de36b-240">パブリック四角形 [PointerDeviceRect](#pointerdevicerect)</span><span class="sxs-lookup"><span data-stu-id="de36b-240">public Rectangle [PointerDeviceRect](#pointerdevicerect)</span></span>

#### <span data-ttu-id="de36b-241">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="de36b-241">PointerFlags</span></span> 

<span data-ttu-id="de36b-242">ポインターイベントの PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="de36b-242">The PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="de36b-243">パブリック uint [PointerFlags](#pointerflags)</span><span class="sxs-lookup"><span data-stu-id="de36b-243">public uint [PointerFlags](#pointerflags)</span></span>

<span data-ttu-id="de36b-244">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-244">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="de36b-245">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="de36b-245">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-246">ポインター Id</span><span class="sxs-lookup"><span data-stu-id="de36b-246">PointerId</span></span> 

<span data-ttu-id="de36b-247">ポインターイベントのポインタ Id。</span><span class="sxs-lookup"><span data-stu-id="de36b-247">The PointerId of the pointer event.</span></span>

> <span data-ttu-id="de36b-248">パブリック uint [ポインター id](#pointerid)</span><span class="sxs-lookup"><span data-stu-id="de36b-248">public uint [PointerId](#pointerid)</span></span>

<span data-ttu-id="de36b-249">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-249">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-250">ポインターの種類</span><span class="sxs-lookup"><span data-stu-id="de36b-250">PointerKind</span></span> 

<span data-ttu-id="de36b-251">ポインターイベントのポインターの種類。</span><span class="sxs-lookup"><span data-stu-id="de36b-251">The PointerKind of the pointer event.</span></span>

> <span data-ttu-id="de36b-252">パブリック uint [ポインターの種類](#pointerkind)</span><span class="sxs-lookup"><span data-stu-id="de36b-252">public uint [PointerKind](#pointerkind)</span></span>

<span data-ttu-id="de36b-253">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-253">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="de36b-254">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="de36b-254">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="de36b-255">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="de36b-255">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="de36b-256">時間</span><span class="sxs-lookup"><span data-stu-id="de36b-256">Time</span></span> 

<span data-ttu-id="de36b-257">ポインターイベントの時刻。</span><span class="sxs-lookup"><span data-stu-id="de36b-257">The Time of the pointer event.</span></span>

> <span data-ttu-id="de36b-258">公開 uint [時間](#time)</span><span class="sxs-lookup"><span data-stu-id="de36b-258">public uint [Time](#time)</span></span>

<span data-ttu-id="de36b-259">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-259">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-260">TouchContact</span><span class="sxs-lookup"><span data-stu-id="de36b-260">TouchContact</span></span> 

<span data-ttu-id="de36b-261">ポインターイベントの TouchContact。</span><span class="sxs-lookup"><span data-stu-id="de36b-261">The TouchContact of the pointer event.</span></span>

> <span data-ttu-id="de36b-262">パブリック四角形 [TouchContact](#touchcontact)</span><span class="sxs-lookup"><span data-stu-id="de36b-262">public Rectangle [TouchContact](#touchcontact)</span></span>

<span data-ttu-id="de36b-263">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-263">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-264">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="de36b-264">TouchContactRaw</span></span> 

<span data-ttu-id="de36b-265">ポインターイベントの TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="de36b-265">The TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="de36b-266">パブリック四角形 [TouchContactRaw](#touchcontactraw)</span><span class="sxs-lookup"><span data-stu-id="de36b-266">public Rectangle [TouchContactRaw](#touchcontactraw)</span></span>

<span data-ttu-id="de36b-267">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-267">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-268">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="de36b-268">TouchFlags</span></span> 

<span data-ttu-id="de36b-269">ポインターイベントの TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="de36b-269">The TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="de36b-270">パブリック uint [TouchFlags](#touchflags)</span><span class="sxs-lookup"><span data-stu-id="de36b-270">public uint [TouchFlags](#touchflags)</span></span>

<span data-ttu-id="de36b-271">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-271">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="de36b-272">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="de36b-272">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-273">TouchMask</span><span class="sxs-lookup"><span data-stu-id="de36b-273">TouchMask</span></span> 

<span data-ttu-id="de36b-274">ポインターイベントの TouchMask。</span><span class="sxs-lookup"><span data-stu-id="de36b-274">The TouchMask of the pointer event.</span></span>

> <span data-ttu-id="de36b-275">パブリック uint [TouchMask](#touchmask)</span><span class="sxs-lookup"><span data-stu-id="de36b-275">public uint [TouchMask](#touchmask)</span></span>

<span data-ttu-id="de36b-276">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-276">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="de36b-277">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="de36b-277">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-278">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="de36b-278">TouchOrientation</span></span> 

<span data-ttu-id="de36b-279">ポインターイベントの TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="de36b-279">The TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="de36b-280">パブリック uint [TouchOrientation](#touchorientation)</span><span class="sxs-lookup"><span data-stu-id="de36b-280">public uint [TouchOrientation](#touchorientation)</span></span>

<span data-ttu-id="de36b-281">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-281">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="de36b-282">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="de36b-282">TouchPressure</span></span> 

<span data-ttu-id="de36b-283">ポインターイベントの TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="de36b-283">The TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="de36b-284">パブリック uint [TouchPressure](#touchpressure)</span><span class="sxs-lookup"><span data-stu-id="de36b-284">public uint [TouchPressure](#touchpressure)</span></span>

<span data-ttu-id="de36b-285">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="de36b-285">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

