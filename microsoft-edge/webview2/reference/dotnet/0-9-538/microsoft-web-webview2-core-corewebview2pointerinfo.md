---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2PointerInfo の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PointerInfo。
ms.openlocfilehash: 9ce4c9c3f076d54f03295ffda84c5fb0f03b4166
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010903"
---
# <span data-ttu-id="a6e94-104">0.9.579 クラスの WebView2 クラス (CoreWebView2PointerInfo)</span><span class="sxs-lookup"><span data-stu-id="a6e94-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2PointerInfo class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="a6e94-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="a6e94-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a6e94-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a6e94-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a6e94-107">これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="a6e94-107">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="a6e94-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a6e94-108">Summary</span></span>

 <span data-ttu-id="a6e94-109">Members</span><span class="sxs-lookup"><span data-stu-id="a6e94-109">Members</span></span>                        | <span data-ttu-id="a6e94-110">説明</span><span class="sxs-lookup"><span data-stu-id="a6e94-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a6e94-111">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="a6e94-111">ButtonChangeKind</span></span>](#buttonchangekind) | <span data-ttu-id="a6e94-112">ポインターイベントの ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="a6e94-112">The ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="a6e94-113">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="a6e94-113">DisplayRect</span></span>](#displayrect) | <span data-ttu-id="a6e94-114">Windows SDK (winuser) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="a6e94-114">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="a6e94-115">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="a6e94-115">FrameId</span></span>](#frameid) | <span data-ttu-id="a6e94-116">ポインターイベントのフレーム Id。</span><span class="sxs-lookup"><span data-stu-id="a6e94-116">The FrameID of the pointer event.</span></span>
[<span data-ttu-id="a6e94-117">場所の HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="a6e94-117">HimetricLocation</span></span>](#himetriclocation) | <span data-ttu-id="a6e94-118">ポインターイベントの HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="a6e94-118">The HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="a6e94-119">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="a6e94-119">HimetricLocationRaw</span></span>](#himetriclocationraw) | <span data-ttu-id="a6e94-120">ポインターイベントのロウ Metriclocation。</span><span class="sxs-lookup"><span data-stu-id="a6e94-120">The HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="a6e94-121">履歴カウント</span><span class="sxs-lookup"><span data-stu-id="a6e94-121">HistoryCount</span></span>](#historycount) | <span data-ttu-id="a6e94-122">ポインターイベントの履歴カウント。</span><span class="sxs-lookup"><span data-stu-id="a6e94-122">The HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="a6e94-123">InputData</span><span class="sxs-lookup"><span data-stu-id="a6e94-123">InputData</span></span>](#inputdata) | <span data-ttu-id="a6e94-124">ポインターイベントの InputData。</span><span class="sxs-lookup"><span data-stu-id="a6e94-124">The InputData of the pointer event.</span></span>
[<span data-ttu-id="a6e94-125">KeyStates</span><span class="sxs-lookup"><span data-stu-id="a6e94-125">KeyStates</span></span>](#keystates) | <span data-ttu-id="a6e94-126">ポインターイベントの KeyStates。</span><span class="sxs-lookup"><span data-stu-id="a6e94-126">The KeyStates of the pointer event.</span></span>
[<span data-ttu-id="a6e94-127">ペンフラグ</span><span class="sxs-lookup"><span data-stu-id="a6e94-127">PenFlags</span></span>](#penflags) | <span data-ttu-id="a6e94-128">ポインターイベントのペンフラグ。</span><span class="sxs-lookup"><span data-stu-id="a6e94-128">The PenFlags of the pointer event.</span></span>
[<span data-ttu-id="a6e94-129">ペンマスク</span><span class="sxs-lookup"><span data-stu-id="a6e94-129">PenMask</span></span>](#penmask) | <span data-ttu-id="a6e94-130">ポインターイベントのペンマスク。</span><span class="sxs-lookup"><span data-stu-id="a6e94-130">The PenMask of the pointer event.</span></span>
[<span data-ttu-id="a6e94-131">ペンの筆圧</span><span class="sxs-lookup"><span data-stu-id="a6e94-131">PenPressure</span></span>](#penpressure) | <span data-ttu-id="a6e94-132">ポインターイベントのペンの筆圧。</span><span class="sxs-lookup"><span data-stu-id="a6e94-132">The PenPressure of the pointer event.</span></span>
[<span data-ttu-id="a6e94-133">ペンの回転</span><span class="sxs-lookup"><span data-stu-id="a6e94-133">PenRotation</span></span>](#penrotation) | <span data-ttu-id="a6e94-134">ポインターイベントのペン回転。</span><span class="sxs-lookup"><span data-stu-id="a6e94-134">The PenRotation of the pointer event.</span></span>
[<span data-ttu-id="a6e94-135">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="a6e94-135">PenTiltX</span></span>](#pentiltx) | <span data-ttu-id="a6e94-136">ポインターイベントの PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="a6e94-136">The PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="a6e94-137">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="a6e94-137">PenTiltY</span></span>](#pentilty) | <span data-ttu-id="a6e94-138">ポインターイベントの PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="a6e94-138">The PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="a6e94-139">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="a6e94-139">PerformanceCount</span></span>](#performancecount) | <span data-ttu-id="a6e94-140">ポインターイベントの PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="a6e94-140">The PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="a6e94-141">ピクセルの位置</span><span class="sxs-lookup"><span data-stu-id="a6e94-141">PixelLocation</span></span>](#pixellocation) | <span data-ttu-id="a6e94-142">ポインターイベントのピクセルの位置。</span><span class="sxs-lookup"><span data-stu-id="a6e94-142">The PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="a6e94-143">ピクセルの場所 Raw</span><span class="sxs-lookup"><span data-stu-id="a6e94-143">PixelLocationRaw</span></span>](#pixellocationraw) | <span data-ttu-id="a6e94-144">ポインターイベントのピクセルの場所。</span><span class="sxs-lookup"><span data-stu-id="a6e94-144">The PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="a6e94-145">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="a6e94-145">PointerDeviceRect</span></span>](#pointerdevicerect) | <span data-ttu-id="a6e94-146">Windows SDK で定義されている POINTER_INFO 構造体の sourceDevice プロパティの PointerDeviceRect です (winuser. h)。</span><span class="sxs-lookup"><span data-stu-id="a6e94-146">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="a6e94-147">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="a6e94-147">PointerFlags</span></span>](#pointerflags) | <span data-ttu-id="a6e94-148">ポインターイベントの PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="a6e94-148">The PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="a6e94-149">ポインター Id</span><span class="sxs-lookup"><span data-stu-id="a6e94-149">PointerId</span></span>](#pointerid) | <span data-ttu-id="a6e94-150">ポインターイベントのポインタ Id。</span><span class="sxs-lookup"><span data-stu-id="a6e94-150">The PointerId of the pointer event.</span></span>
[<span data-ttu-id="a6e94-151">ポインターの種類</span><span class="sxs-lookup"><span data-stu-id="a6e94-151">PointerKind</span></span>](#pointerkind) | <span data-ttu-id="a6e94-152">ポインターイベントのポインターの種類。</span><span class="sxs-lookup"><span data-stu-id="a6e94-152">The PointerKind of the pointer event.</span></span>
[<span data-ttu-id="a6e94-153">時間</span><span class="sxs-lookup"><span data-stu-id="a6e94-153">Time</span></span>](#time) | <span data-ttu-id="a6e94-154">ポインターイベントの時刻。</span><span class="sxs-lookup"><span data-stu-id="a6e94-154">The Time of the pointer event.</span></span>
[<span data-ttu-id="a6e94-155">TouchContact</span><span class="sxs-lookup"><span data-stu-id="a6e94-155">TouchContact</span></span>](#touchcontact) | <span data-ttu-id="a6e94-156">ポインターイベントの TouchContact。</span><span class="sxs-lookup"><span data-stu-id="a6e94-156">The TouchContact of the pointer event.</span></span>
[<span data-ttu-id="a6e94-157">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="a6e94-157">TouchContactRaw</span></span>](#touchcontactraw) | <span data-ttu-id="a6e94-158">ポインターイベントの TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="a6e94-158">The TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="a6e94-159">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="a6e94-159">TouchFlags</span></span>](#touchflags) | <span data-ttu-id="a6e94-160">ポインターイベントの TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="a6e94-160">The TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="a6e94-161">TouchMask</span><span class="sxs-lookup"><span data-stu-id="a6e94-161">TouchMask</span></span>](#touchmask) | <span data-ttu-id="a6e94-162">ポインターイベントの TouchMask。</span><span class="sxs-lookup"><span data-stu-id="a6e94-162">The TouchMask of the pointer event.</span></span>
[<span data-ttu-id="a6e94-163">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="a6e94-163">TouchOrientation</span></span>](#touchorientation) | <span data-ttu-id="a6e94-164">ポインターイベントの TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="a6e94-164">The TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="a6e94-165">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="a6e94-165">TouchPressure</span></span>](#touchpressure) | <span data-ttu-id="a6e94-166">ポインターイベントの TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="a6e94-166">The TouchPressure of the pointer event.</span></span>

## <span data-ttu-id="a6e94-167">Members</span><span class="sxs-lookup"><span data-stu-id="a6e94-167">Members</span></span>

#### <span data-ttu-id="a6e94-168">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="a6e94-168">ButtonChangeKind</span></span> 

<span data-ttu-id="a6e94-169">ポインターイベントの ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="a6e94-169">The ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="a6e94-170">パブリック int [ボタンの Changekind](#buttonchangekind)</span><span class="sxs-lookup"><span data-stu-id="a6e94-170">public int [ButtonChangeKind](#buttonchangekind)</span></span>

<span data-ttu-id="a6e94-171">これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-171">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="a6e94-172">この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6e94-172">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-173">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="a6e94-173">DisplayRect</span></span> 

<span data-ttu-id="a6e94-174">Windows SDK (winuser) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="a6e94-174">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="a6e94-175">パブリック Rect [Displayrect](#displayrect)</span><span class="sxs-lookup"><span data-stu-id="a6e94-175">public Rect [DisplayRect](#displayrect)</span></span>

#### <span data-ttu-id="a6e94-176">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="a6e94-176">FrameId</span></span> 

<span data-ttu-id="a6e94-177">ポインターイベントのフレーム Id。</span><span class="sxs-lookup"><span data-stu-id="a6e94-177">The FrameID of the pointer event.</span></span>

> <span data-ttu-id="a6e94-178">パブリック uint [フレーム id](#frameid)</span><span class="sxs-lookup"><span data-stu-id="a6e94-178">public uint [FrameId](#frameid)</span></span>

<span data-ttu-id="a6e94-179">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-179">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-180">場所の HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="a6e94-180">HimetricLocation</span></span> 

<span data-ttu-id="a6e94-181">ポインターイベントの HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="a6e94-181">The HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="a6e94-182">パブリックポイントの [Himetriclocation](#himetriclocation)</span><span class="sxs-lookup"><span data-stu-id="a6e94-182">public Point [HimetricLocation](#himetriclocation)</span></span>

<span data-ttu-id="a6e94-183">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-183">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-184">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="a6e94-184">HimetricLocationRaw</span></span> 

<span data-ttu-id="a6e94-185">ポインターイベントのロウ Metriclocation。</span><span class="sxs-lookup"><span data-stu-id="a6e94-185">The HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="a6e94-186">パブリックポイントの [Himetriclocationraw](#himetriclocationraw)</span><span class="sxs-lookup"><span data-stu-id="a6e94-186">public Point [HimetricLocationRaw](#himetriclocationraw)</span></span>

<span data-ttu-id="a6e94-187">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-187">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-188">履歴カウント</span><span class="sxs-lookup"><span data-stu-id="a6e94-188">HistoryCount</span></span> 

<span data-ttu-id="a6e94-189">ポインターイベントの履歴カウント。</span><span class="sxs-lookup"><span data-stu-id="a6e94-189">The HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="a6e94-190">パブリック uint [履歴カウント](#historycount)</span><span class="sxs-lookup"><span data-stu-id="a6e94-190">public uint [HistoryCount](#historycount)</span></span>

<span data-ttu-id="a6e94-191">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-191">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-192">InputData</span><span class="sxs-lookup"><span data-stu-id="a6e94-192">InputData</span></span> 

<span data-ttu-id="a6e94-193">ポインターイベントの InputData。</span><span class="sxs-lookup"><span data-stu-id="a6e94-193">The InputData of the pointer event.</span></span>

> <span data-ttu-id="a6e94-194">パブリック int の [Inputdata](#inputdata)</span><span class="sxs-lookup"><span data-stu-id="a6e94-194">public int [InputData](#inputdata)</span></span>

<span data-ttu-id="a6e94-195">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-195">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-196">KeyStates</span><span class="sxs-lookup"><span data-stu-id="a6e94-196">KeyStates</span></span> 

<span data-ttu-id="a6e94-197">ポインターイベントの KeyStates。</span><span class="sxs-lookup"><span data-stu-id="a6e94-197">The KeyStates of the pointer event.</span></span>

> <span data-ttu-id="a6e94-198">パブリック uint [Keystates](#keystates)</span><span class="sxs-lookup"><span data-stu-id="a6e94-198">public uint [KeyStates](#keystates)</span></span>

<span data-ttu-id="a6e94-199">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-199">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-200">ペンフラグ</span><span class="sxs-lookup"><span data-stu-id="a6e94-200">PenFlags</span></span> 

<span data-ttu-id="a6e94-201">ポインターイベントのペンフラグ。</span><span class="sxs-lookup"><span data-stu-id="a6e94-201">The PenFlags of the pointer event.</span></span>

> <span data-ttu-id="a6e94-202">パブリック uint の [フラグ](#penflags)</span><span class="sxs-lookup"><span data-stu-id="a6e94-202">public uint [PenFlags](#penflags)</span></span>

<span data-ttu-id="a6e94-203">これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-203">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="a6e94-204">これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6e94-204">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-205">ペンマスク</span><span class="sxs-lookup"><span data-stu-id="a6e94-205">PenMask</span></span> 

<span data-ttu-id="a6e94-206">ポインターイベントのペンマスク。</span><span class="sxs-lookup"><span data-stu-id="a6e94-206">The PenMask of the pointer event.</span></span>

> <span data-ttu-id="a6e94-207">パブリック uint の [マスク](#penmask)</span><span class="sxs-lookup"><span data-stu-id="a6e94-207">public uint [PenMask](#penmask)</span></span>

<span data-ttu-id="a6e94-208">これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="a6e94-208">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="a6e94-209">これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6e94-209">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-210">ペンの筆圧</span><span class="sxs-lookup"><span data-stu-id="a6e94-210">PenPressure</span></span> 

<span data-ttu-id="a6e94-211">ポインターイベントのペンの筆圧。</span><span class="sxs-lookup"><span data-stu-id="a6e94-211">The PenPressure of the pointer event.</span></span>

> <span data-ttu-id="a6e94-212">公開 uint の [気圧](#penpressure)</span><span class="sxs-lookup"><span data-stu-id="a6e94-212">public uint [PenPressure](#penpressure)</span></span>

<span data-ttu-id="a6e94-213">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-213">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-214">ペンの回転</span><span class="sxs-lookup"><span data-stu-id="a6e94-214">PenRotation</span></span> 

<span data-ttu-id="a6e94-215">ポインターイベントのペン回転。</span><span class="sxs-lookup"><span data-stu-id="a6e94-215">The PenRotation of the pointer event.</span></span>

> <span data-ttu-id="a6e94-216">公開 uint の [回転](#penrotation)</span><span class="sxs-lookup"><span data-stu-id="a6e94-216">public uint [PenRotation](#penrotation)</span></span>

<span data-ttu-id="a6e94-217">これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-217">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-218">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="a6e94-218">PenTiltX</span></span> 

<span data-ttu-id="a6e94-219">ポインターイベントの PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="a6e94-219">The PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="a6e94-220">パブリック int [PenTiltX](#pentiltx)</span><span class="sxs-lookup"><span data-stu-id="a6e94-220">public int [PenTiltX](#pentiltx)</span></span>

<span data-ttu-id="a6e94-221">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-221">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-222">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="a6e94-222">PenTiltY</span></span> 

<span data-ttu-id="a6e94-223">ポインターイベントの PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="a6e94-223">The PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="a6e94-224">パブリック int [PenTiltY](#pentilty)</span><span class="sxs-lookup"><span data-stu-id="a6e94-224">public int [PenTiltY](#pentilty)</span></span>

<span data-ttu-id="a6e94-225">これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-225">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-226">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="a6e94-226">PerformanceCount</span></span> 

<span data-ttu-id="a6e94-227">ポインターイベントの PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="a6e94-227">The PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="a6e94-228">パブリック ulong [PerformanceCount](#performancecount)</span><span class="sxs-lookup"><span data-stu-id="a6e94-228">public ulong [PerformanceCount](#performancecount)</span></span>

<span data-ttu-id="a6e94-229">これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-229">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-230">ピクセルの位置</span><span class="sxs-lookup"><span data-stu-id="a6e94-230">PixelLocation</span></span> 

<span data-ttu-id="a6e94-231">ポインターイベントのピクセルの位置。</span><span class="sxs-lookup"><span data-stu-id="a6e94-231">The PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="a6e94-232">パブリックポイントの [ピクセルの位置](#pixellocation)</span><span class="sxs-lookup"><span data-stu-id="a6e94-232">public Point [PixelLocation](#pixellocation)</span></span>

<span data-ttu-id="a6e94-233">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-233">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-234">ピクセルの場所 Raw</span><span class="sxs-lookup"><span data-stu-id="a6e94-234">PixelLocationRaw</span></span> 

<span data-ttu-id="a6e94-235">ポインターイベントのピクセルの場所。</span><span class="sxs-lookup"><span data-stu-id="a6e94-235">The PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="a6e94-236">パブリックポイントのピクセルの位置の [raw](#pixellocationraw)</span><span class="sxs-lookup"><span data-stu-id="a6e94-236">public Point [PixelLocationRaw](#pixellocationraw)</span></span>

<span data-ttu-id="a6e94-237">これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-237">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-238">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="a6e94-238">PointerDeviceRect</span></span> 

<span data-ttu-id="a6e94-239">Windows SDK で定義されている POINTER_INFO 構造体の sourceDevice プロパティの PointerDeviceRect です (winuser. h)。</span><span class="sxs-lookup"><span data-stu-id="a6e94-239">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="a6e94-240">パブリック Rect [PointerDeviceRect](#pointerdevicerect)</span><span class="sxs-lookup"><span data-stu-id="a6e94-240">public Rect [PointerDeviceRect](#pointerdevicerect)</span></span>

#### <span data-ttu-id="a6e94-241">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="a6e94-241">PointerFlags</span></span> 

<span data-ttu-id="a6e94-242">ポインターイベントの PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="a6e94-242">The PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="a6e94-243">パブリック uint [PointerFlags](#pointerflags)</span><span class="sxs-lookup"><span data-stu-id="a6e94-243">public uint [PointerFlags](#pointerflags)</span></span>

<span data-ttu-id="a6e94-244">これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-244">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="a6e94-245">これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6e94-245">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-246">ポインター Id</span><span class="sxs-lookup"><span data-stu-id="a6e94-246">PointerId</span></span> 

<span data-ttu-id="a6e94-247">ポインターイベントのポインタ Id。</span><span class="sxs-lookup"><span data-stu-id="a6e94-247">The PointerId of the pointer event.</span></span>

> <span data-ttu-id="a6e94-248">パブリック uint [ポインター id](#pointerid)</span><span class="sxs-lookup"><span data-stu-id="a6e94-248">public uint [PointerId](#pointerid)</span></span>

<span data-ttu-id="a6e94-249">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-249">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-250">ポインターの種類</span><span class="sxs-lookup"><span data-stu-id="a6e94-250">PointerKind</span></span> 

<span data-ttu-id="a6e94-251">ポインターイベントのポインターの種類。</span><span class="sxs-lookup"><span data-stu-id="a6e94-251">The PointerKind of the pointer event.</span></span>

> <span data-ttu-id="a6e94-252">パブリック uint [ポインターの種類](#pointerkind)</span><span class="sxs-lookup"><span data-stu-id="a6e94-252">public uint [PointerKind](#pointerkind)</span></span>

<span data-ttu-id="a6e94-253">これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-253">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="a6e94-254">この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6e94-254">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="a6e94-255">PT_PEN と PT_TOUCH をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e94-255">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="a6e94-256">時間</span><span class="sxs-lookup"><span data-stu-id="a6e94-256">Time</span></span> 

<span data-ttu-id="a6e94-257">ポインターイベントの時刻。</span><span class="sxs-lookup"><span data-stu-id="a6e94-257">The Time of the pointer event.</span></span>

> <span data-ttu-id="a6e94-258">公開 uint [時間](#time)</span><span class="sxs-lookup"><span data-stu-id="a6e94-258">public uint [Time](#time)</span></span>

<span data-ttu-id="a6e94-259">これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-259">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-260">TouchContact</span><span class="sxs-lookup"><span data-stu-id="a6e94-260">TouchContact</span></span> 

<span data-ttu-id="a6e94-261">ポインターイベントの TouchContact。</span><span class="sxs-lookup"><span data-stu-id="a6e94-261">The TouchContact of the pointer event.</span></span>

> <span data-ttu-id="a6e94-262">パブリック Rect [TouchContact](#touchcontact)</span><span class="sxs-lookup"><span data-stu-id="a6e94-262">public Rect [TouchContact](#touchcontact)</span></span>

<span data-ttu-id="a6e94-263">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-263">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-264">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="a6e94-264">TouchContactRaw</span></span> 

<span data-ttu-id="a6e94-265">ポインターイベントの TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="a6e94-265">The TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="a6e94-266">パブリック Rect [TouchContactRaw](#touchcontactraw)</span><span class="sxs-lookup"><span data-stu-id="a6e94-266">public Rect [TouchContactRaw](#touchcontactraw)</span></span>

<span data-ttu-id="a6e94-267">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-267">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-268">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="a6e94-268">TouchFlags</span></span> 

<span data-ttu-id="a6e94-269">ポインターイベントの TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="a6e94-269">The TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="a6e94-270">パブリック uint [TouchFlags](#touchflags)</span><span class="sxs-lookup"><span data-stu-id="a6e94-270">public uint [TouchFlags](#touchflags)</span></span>

<span data-ttu-id="a6e94-271">これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-271">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="a6e94-272">これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6e94-272">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-273">TouchMask</span><span class="sxs-lookup"><span data-stu-id="a6e94-273">TouchMask</span></span> 

<span data-ttu-id="a6e94-274">ポインターイベントの TouchMask。</span><span class="sxs-lookup"><span data-stu-id="a6e94-274">The TouchMask of the pointer event.</span></span>

> <span data-ttu-id="a6e94-275">パブリック uint [TouchMask](#touchmask)</span><span class="sxs-lookup"><span data-stu-id="a6e94-275">public uint [TouchMask](#touchmask)</span></span>

<span data-ttu-id="a6e94-276">これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-276">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="a6e94-277">これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6e94-277">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-278">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="a6e94-278">TouchOrientation</span></span> 

<span data-ttu-id="a6e94-279">ポインターイベントの TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="a6e94-279">The TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="a6e94-280">パブリック uint [TouchOrientation](#touchorientation)</span><span class="sxs-lookup"><span data-stu-id="a6e94-280">public uint [TouchOrientation](#touchorientation)</span></span>

<span data-ttu-id="a6e94-281">これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-281">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="a6e94-282">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="a6e94-282">TouchPressure</span></span> 

<span data-ttu-id="a6e94-283">ポインターイベントの TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="a6e94-283">The TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="a6e94-284">パブリック uint [TouchPressure](#touchpressure)</span><span class="sxs-lookup"><span data-stu-id="a6e94-284">public uint [TouchPressure](#touchpressure)</span></span>

<span data-ttu-id="a6e94-285">これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e94-285">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

