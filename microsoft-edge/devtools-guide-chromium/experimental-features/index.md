---
description: Microsoft Edge DevTools の最新の実験的機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
ms.openlocfilehash: fbdeeb08599285a9cfa6edd467282cfbabbadd74
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234705"
---
# <span data-ttu-id="8d7d5-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="8d7d5-104">Experimental features</span></span>  

<span data-ttu-id="8d7d5-105">Microsoft Edge DevTools は、まだ開発中の試験的な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="8d7d5-106">各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="8d7d5-107">試験的な機能は Microsoft Edge のすべてのチャネルで利用できます。Microsoft Edge Canary チャネルを使用すると、最新の試験的な機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="8d7d5-108">試験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-108">Turn on experimental features</span></span>  

<span data-ttu-id="8d7d5-109">Microsoft Edge で実験的な機能 \(またはオフ\) を有効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="8d7d5-110">[DevTools を開きます][DevtoolsOpenMain]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-110">[Open DevTools][DevtoolsOpenMain].</span></span>  
    *   <span data-ttu-id="8d7d5-111">`Control` + `Shift` + `I` \(Windows,Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="8d7d5-112">詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="8d7d5-113">[設定] [ウィンドウを開][DevToolsCustomizeSettings] きます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="8d7d5-114">選択します `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="8d7d5-115">詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="8d7d5-116">[設定] ウィンドウの左側 **で** 、[実験] **セクションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="DevTools の設定の実験の一覧" lightbox="../media/experiments-devtools.msft.png":::
       <span data-ttu-id="8d7d5-118">DevTools の設定の実験の **一覧**</span><span class="sxs-lookup"><span data-stu-id="8d7d5-118">List of experiments in DevTools **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8d7d5-119">[ **実験] ページで** 、利用可能なすべての試験的な機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="8d7d5-120">Microsoft Edge DevTools を閉じてから再度開きます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="8d7d5-121">試験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="8d7d5-122">試験的な機能をオフにする場合は、[ **実験** ] ページを開き、無効にする試験的な機能のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="8d7d5-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="8d7d5-123">Highlighted experimental features</span></span>  

<span data-ttu-id="8d7d5-124">次のセクションでは、Microsoft Edge で使用可能な新しい試験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="8d7d5-125">試験的機能</span><span class="sxs-lookup"><span data-stu-id="8d7d5-125">Experimental feature</span></span> | <span data-ttu-id="8d7d5-126">Microsoft Edge のバージョン</span><span class="sxs-lookup"><span data-stu-id="8d7d5-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="8d7d5-127">エミュレーション: デュアル スクリーン モードのサポート</span><span class="sxs-lookup"><span data-stu-id="8d7d5-127">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="8d7d5-128">84 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-128">84 or later</span></span> |  
| [<span data-ttu-id="8d7d5-129">新しい CSS グリッド デバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-129">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="8d7d5-130">85 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-130">85 or later</span></span> |  
| [<span data-ttu-id="8d7d5-131">パネル間でタブを移動するサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-131">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="8d7d5-132">85 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-132">85 or later</span></span> |  
| [<span data-ttu-id="8d7d5-133">webhint を有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-133">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="8d7d5-134">85 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-134">85 or later</span></span> |  
| [<span data-ttu-id="8d7d5-135">ネットワーク コンソールを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-135">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="8d7d5-136">85 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-136">85 or later</span></span> |  
| [<span data-ttu-id="8d7d5-137">ソース オーダー ビューアー</span><span class="sxs-lookup"><span data-stu-id="8d7d5-137">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="8d7d5-138">86 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-138">86 or later</span></span> |  
| [<span data-ttu-id="8d7d5-139">キーボード ショートカット エディターを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-139">Enable keyboard shortcut editor</span></span>](#enable-keyboard-shortcut-editor) | <span data-ttu-id="8d7d5-140">87 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-140">87 or later</span></span> |  
| [<span data-ttu-id="8d7d5-141">3D ビューで複合レイヤーを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-141">Turn on Composited Layers in 3D View</span></span>](#turn-on-composited-layers-in-3d-view) | <span data-ttu-id="8d7d5-142">87 以降</span><span class="sxs-lookup"><span data-stu-id="8d7d5-142">87 or later</span></span> |  

### <span data-ttu-id="8d7d5-143">エミュレーション: デュアル スクリーン モードのサポート</span><span class="sxs-lookup"><span data-stu-id="8d7d5-143">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="8d7d5-144">Microsoft Edge で 2 つの新しいデュアルスクリーン デバイスと折りたたみ可能なデバイスを適用する追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-144">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="8d7d5-145">Surface の一方</span><span class="sxs-lookup"><span data-stu-id="8d7d5-145">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="8d7d5-146">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="8d7d5-146">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  
    
<span data-ttu-id="8d7d5-147">デバイスをエミュレートし、次の状態を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-147">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="8d7d5-148">単一画面または折りたたまれた状態</span><span class="sxs-lookup"><span data-stu-id="8d7d5-148">Single-screen or folded posture</span></span>  
*   <span data-ttu-id="8d7d5-149">デュアルスクリーンまたは展開された体勢</span><span class="sxs-lookup"><span data-stu-id="8d7d5-149">Dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="8d7d5-150">試験[的な Web プラットフォーム API](#enable-experimental-apis)を有効にし[、CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用して、デュアルスクリーンと折りたたみ可能なデバイス向けの Web サイト \(または app\) を強化します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-150">[Enable experimental Web Platform APIs](#enable-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="Microsoft Edge で Surface をエミュレートする" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="8d7d5-152">Microsoft Edge で Surface をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-152">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="8d7d5-153">試験的な API を有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-153">Enable experimental APIs</span></span>  

<span data-ttu-id="8d7d5-154">[CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用するには、Microsoft Edge でフラグ `Experimental Web Platform features` をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-154">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="8d7d5-155">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-155">Complete the following steps.</span></span>  

1.  <span data-ttu-id="8d7d5-156">に移動します `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-156">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="8d7d5-157">[検索フラグ **] ボックスに**、「試験的な Web プラットフォーム機能」フラグを入力し、[無効] を [有効] `Experimental Web Platform features` に**変更します**。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8d7d5-157">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="8d7d5-158">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-158">Restart Microsoft Edge.</span></span>  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="[試験的な Web プラットフォーム機能] フラグを有効にする" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="8d7d5-160">[試験的な Web プラットフォーム機能] フラグを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-160">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="8d7d5-161">[CSS][DualScreenDocsCssMedia]メディア クエリまたは[JavaScript Windows セグメント][DualScreenDocsJSAPI]列挙 API を使用して、Surface Surface の Web サイトまたはアプリを強化する場合は[、Surface Surface][SurfaceDevicesDuo] [デバイス][SurfaceDevicesDuo]の Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリで試験的な**Web**プラットフォーム機能フラグも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-161">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="8d7d5-162">デスクトップの[Microsoft][MicrosoftEdge] [Edge][SurfaceDevicesDuo]で試験**的な Web**プラットフォーム機能のフラグが有効になっている場合[、Android Microsoft Edge][GooglePlayMicrosoftEdge]アプリで無効になっている場合、デスクトップの Surface Emulator の Web サイトまたはアプリの動作が、Microsoft Edge のデスクトップの Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリと一致しません。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-162">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="8d7d5-163">フラグが Android とデスクトップの Microsoft Edge で一致し、デスクトップの Microsoft Edge で Surface Emulator エミュレーターが正常に使用 [されたことを確認します][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-163">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="8d7d5-164">折りたたみ可能なデュアルスクリーン デバイスでのテスト</span><span class="sxs-lookup"><span data-stu-id="8d7d5-164">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="8d7d5-165">Microsoft Edge でデュアルスクリーンの位置で [Surface Over][SurfaceDevicesDuo] をエミュレートすると、Web サイトまたはアプリの上に、"2 つの画面の間のスペース\" という円が描画されます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-165">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="8d7d5-166">エミュレートされた表示は、Surface Surface で実行されている [Microsoft Edge Android][GooglePlayMicrosoftEdge] アプリで Web サイト \(または app\) がレンダリングされる方法と [一致します][SurfaceDevicesDuo]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-166">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] running on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="8d7d5-167">Web サイト \(または app\) を更新して、より良い画面を表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-167">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="8d7d5-168">For more information about adapting your website \(or app\) to the navigate to [How to work with the windows.][DualScreenIntroductionHowWorkSeam]</span><span class="sxs-lookup"><span data-stu-id="8d7d5-168">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam].</span></span>  

<span data-ttu-id="8d7d5-169">デバイス [ツール バーには、][DevtoolsDeviceModeIndexSimulateMobileViewport] 複数の位置と向きで Web サイトまたはアプリをテストするのに役立つ追加機能があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-169">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="8d7d5-170">ビューポート **を横向** きに回転するには、回転 ![ ][ImageRotateIcon] \( Rotate \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-170">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="8d7d5-171">機能を Span \( **Span** \) と組み合わせて、単一画面または折りたたまれた状態とデュアルスクリーンまたは展開された状態を ![ 切り ][ImageSpanIcon] 替える。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-171">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="8d7d5-172">これらの機能を組み合わせて、4 つの考えられるすべての位置と向きで Web サイトまたはアプリをテストできます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-172">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="8d7d5-174">デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス</span><span class="sxs-lookup"><span data-stu-id="8d7d5-174">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="8d7d5-175">Experimental **Web プラットフォーム機能** \( ExperimentalApis \) アイコンには、Experimental Web Platform 機能 ![ フラグの ][ImageExperimentalApisIcon] **状態が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-175">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="8d7d5-176">フラグがオンの場合、アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-176">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="8d7d5-177">フラグがオフの場合、アイコンは強調表示されません。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-177">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="8d7d5-178">フラグを \(または off\) に切り替えるには、フラグに移動 `edge://flags` して切り替えます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-178">To turn on \(or off\) the flag, navigate to `edge://flags` and toggle the flag.</span></span>  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

<span data-ttu-id="8d7d5-179">ここでは、デュアルスクリーン デバイス用に Web サイト \(または app\) を強化するのに役立つ可能性があるその他のリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-179">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices.</span></span>  

*   <span data-ttu-id="8d7d5-180">デュアルスクリーン デバイスでの Web 開発の詳細については、「デュアルスクリーン Web [エクスペリエンス」に移動してください][DualScreenWebIndex]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-180">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="8d7d5-181">Surface [Emulator エミュレーターをインストールします][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-181">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="8d7d5-182">Microsoft Edge のエミュレーターとは異なるので、Android を実行している Surface Surface をエミュレートし [、Android Studio と統合します][AndroidDeveloperStudio]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-182">It is different from the emulator in Microsoft Edge, emulates the Surface Duo running Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="8d7d5-183">詳しくは [、Surface Sdk の取得に関するページをご覧ください][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-183">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  
    
> [!NOTE]
> <span data-ttu-id="8d7d5-184">現在の既知の問題の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-184">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="8d7d5-185">[Microsoft][RemoteDesktopClientDocs]リモート デスクトップ クライアントを使用してリモート PC に接続し[、Surface Galaxy][SurfaceDevicesDuo]または Samsung Galaxy [Fold][SamsungMobileGalaxyFold]をエミュレートする場合、ポインターが動く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-185">When using a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="8d7d5-186">If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-186">If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).</span></span>  

### <span data-ttu-id="8d7d5-187">新しい CSS グリッド デバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-187">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="8d7d5-188">この試験的な機能は、CSS グリッド レイアウトのデバッグに役立つ新しい視覚エフェクトを多数提供します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-188">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="8d7d5-189">最新の試験的な機能をプレビューするには、 [この実験を有効に](#turn-on-experimental-features) し、DevTools を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-189">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="8d7d5-190">この実験は、Microsoft Edge バージョン 87 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-190">This experiment is on by default in Microsoft Edge version 87 or later.</span></span>  

#### <span data-ttu-id="8d7d5-191">検査ツールを使用した、ホバー時のグリッド オーバーレイの表示</span><span class="sxs-lookup"><span data-stu-id="8d7d5-191">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="8d7d5-192">検査 **ツール** を使用すると、Web サイト内の CSS グリッド レイアウトをマウスでポイントすることで、簡単に識別して視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-192">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="8d7d5-193">DevTools **の左上隅** にある Inspect ![ \( Inspect ][ImageInspectIcon] \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-193">Choose the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="8d7d5-194">次に、デバッグする Web サイトの Grid 要素をポイントします。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-194">Then, hover over a Grid element on the website you are debugging.</span></span>  <span data-ttu-id="8d7d5-195">枠線はグリッドの周囲に表示され、網かけはグリッドのギャップがある場合の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-195">Outlines are displayed around the grid, and shading indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="../media/grid-inspect.msft.png" alt-text="検査ツールを使用してグリッドを表示する" lightbox="../media/grid-inspect.msft.png":::
   <span data-ttu-id="8d7d5-197">検査ツールを使用してグリッド **を表示** する</span><span class="sxs-lookup"><span data-stu-id="8d7d5-197">Viewing grids with the **Inspect** tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="8d7d5-198">固定グリッド オーバーレイの表示</span><span class="sxs-lookup"><span data-stu-id="8d7d5-198">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="8d7d5-199">Microsoft Edge バージョン 86 以降では、試験的な CSS グリッド機能を使用して、永続的なグリッド オーバーレイを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-199">In Microsoft Edge version 86 or later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="8d7d5-200">永続的なオーバーレイには、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-200">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="8d7d5-201">永続的なオーバーレイは、スクロール、マウスの移動、DevTools のその他の機能の使用時にページに表示されたままです。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-201">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="8d7d5-202">複数の固定オーバーレイを同時に有効にすることができ、複数のグリッド レイアウトを一度に確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-202">Multiple persistent overlays can be enabled at the same time, allowing you to review several grid layouts at once.</span></span>  
*   <span data-ttu-id="8d7d5-203">永続的なオーバーレイには、グリッド領域での名前の非表示や表示、グリッド のギャップ、トラックのサイズなど、多くの構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-203">Persistent overlays offer many configuration options, such as hiding or showing names in the grid area, grid gaps, track sizes, and so on.</span></span>  
    
<span data-ttu-id="8d7d5-204">固定グリッド オーバーレイを切り替える 2 つの方法。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-204">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="8d7d5-205">要素ツール **の DOM** ツリーに表示される Grid 要素の横にある Grid 楕円アイコンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-205">Choose the **Grid** oval icon next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="../media/grid-adorner.msft.png" alt-text="要素ツールのグリッド楕円アイコン" lightbox="../media/grid-adorner.msft.png":::
       <span data-ttu-id="8d7d5-207">要素ツールのグリッド楕 **円** アイコン</span><span class="sxs-lookup"><span data-stu-id="8d7d5-207">Grid oval icon in **Elements** tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="8d7d5-208">要素ツール **にある新しいレイアウト** パネルを開き、強調表示する各 Grid 要素の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-208">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="../media/grid-layout-zoom.msft.png" alt-text="DevTools のレイアウト パネル" lightbox="../media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="8d7d5-210">\*\*\*\* DevTools のレイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="8d7d5-210">**Layout** panel in DevTools</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="8d7d5-211">永続的なオーバーレイの構成</span><span class="sxs-lookup"><span data-stu-id="8d7d5-211">Configuring persistent overlays</span></span>  

<span data-ttu-id="8d7d5-212">Microsoft Edge バージョン 86 以降では、新しい**レイアウト**パネルは\*\*\*\*[スタイル] タブと [計算] タブと共に**要素ツール\*\*\*\*にあります**。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-212">In Microsoft Edge version 86 or later, the new **Layout** panel is located in the **Elements** tool alongside the **Styles** and **Computed** tabs.</span></span>  <span data-ttu-id="8d7d5-213">レイアウト **パネルは** 、永続的なオーバーレイの構成オプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-213">The **Layout** panel surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="../media/experiments-grid.msft.png" alt-text="CSS グリッド デバッグ機能" lightbox="../media/experiments-grid.msft.png":::
   <span data-ttu-id="8d7d5-215">CSS グリッド デバッグ機能</span><span class="sxs-lookup"><span data-stu-id="8d7d5-215">CSS grid debugging feature</span></span>  
:::image-end:::  

### <span data-ttu-id="8d7d5-216">パネル間でタブを移動するサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-216">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="8d7d5-217">通常 **、Elements** や **Network** などのツールは、DevTools の上部にあるメイン パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-217">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="8d7d5-218">**3D ビュー**や問題\*\*\*\* のようなツール。通常は DevTools\*\*\*\* の下部にあるドロワー パネルでのみ開きます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-218">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="8d7d5-219">実験を選択した後、上部と下部のパネルの間でツールを移動できます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-219">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="8d7d5-220">ツールを移動するには、タブをポイントし、コンテキスト メニュー \(右クリック\) を開\*\*\*\* き、[上へ移動] または [下へ移動] を選択**します**。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-220">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="8d7d5-221">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-221">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="8d7d5-222">ドロワー パネルを表示または非表示 **にする** 場合は、次を選択します `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-222">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="../media/experiments-move-panels.msft.png" alt-text="パネル間でのタブの移動" lightbox="../media/experiments-move-panels.msft.png":::
   <span data-ttu-id="8d7d5-224">パネル間でのタブの移動</span><span class="sxs-lookup"><span data-stu-id="8d7d5-224">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="8d7d5-225">webhint を有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-225">Enable webhint</span></span>  

<span data-ttu-id="8d7d5-226">[webhint は][WebhintMain] 、Web サイトとローカル Web ページにリアルタイムのフィードバックを提供するオープン ソース ツールです。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-226">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="8d7d5-227">Webhint によって提供される [フィードバックの種類][WebhintMain]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-227">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="8d7d5-228">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="8d7d5-228">accessibility</span></span>  
*   <span data-ttu-id="8d7d5-229">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="8d7d5-229">cross-browser compatibility</span></span>  
*   <span data-ttu-id="8d7d5-230">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8d7d5-230">security</span></span>  
*   <span data-ttu-id="8d7d5-231">performance</span><span class="sxs-lookup"><span data-stu-id="8d7d5-231">performance</span></span>  
*   <span data-ttu-id="8d7d5-232">段階的な Web アプリ (PAS)</span><span class="sxs-lookup"><span data-stu-id="8d7d5-232">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="8d7d5-233">その他の一般的な Web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="8d7d5-233">other common web development issues</span></span>  
    
<span data-ttu-id="8d7d5-234">[webhint 実験は][WebhintMain]、[問題] パネルに webhint フィードバック[を表示][DevtoolsIssues]します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-234">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="8d7d5-235">問題を選択して、ソリューション ドキュメントと、Web サイト上の影響を受けるリソースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-235">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="8d7d5-236">DevTools で関連する\*\*\*\*[ネットワーク] ウィンドウ、[ソース] ウィンドウ、**または**[**要素**] ウィンドウを開くリソース リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-236">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../media/experiments-webhint.msft.png":::
   <span data-ttu-id="8d7d5-238">[問題] パネルの **webhint** フィードバック</span><span class="sxs-lookup"><span data-stu-id="8d7d5-238">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="8d7d5-239">ネットワーク コンソールを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-239">Enable Network Console</span></span>  

<span data-ttu-id="8d7d5-240">**ネットワーク コンソール** は、HTTP を使用して合成ネットワーク要求を行う実験の動作タイトルです。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-240">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="8d7d5-241">ネットワーク コンソールの実験 **を使用して** 、Web API 要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-241">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="8d7d5-242">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-242">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="8d7d5-243">ネットワーク コンソールを **使用するには、次**の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-243">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="8d7d5-244">[ネットワーク] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-244">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="8d7d5-245">変更するネットワーク要求を検索し、再送信します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-245">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="8d7d5-246">コンテキスト メニュー \(右クリック\) を開き、[編集と再生] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-246">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="8d7d5-247">ネットワーク コンソール **が開いたら** 、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-247">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="8d7d5-248">Choose **Send**.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-248">Choose **Send**.</span></span>  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="コンソール ドロワーのネットワーク コンソール" lightbox="../media/network-network-console.msft.png":::
   <span data-ttu-id="8d7d5-250">**コンソール ドロワー\*\*\*\*のネットワーク**コンソール</span><span class="sxs-lookup"><span data-stu-id="8d7d5-250">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="8d7d5-251">ソース オーダー ビューアー</span><span class="sxs-lookup"><span data-stu-id="8d7d5-251">Source Order Viewer</span></span>  

<span data-ttu-id="8d7d5-252">**ソース オーダー ビューアーは** 、ページ ソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-252">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="8d7d5-253">スクリーン リーダーとキーボード のユーザーを混乱させるソースの順序と、画面の表示順序が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-253">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="8d7d5-254">ソース オーダー **ビューアーの実験を** 使用して、画面の表示順序とソースの順序の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-254">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="8d7d5-255">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-255">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="8d7d5-256">ソース オーダー **ビューアーを使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-256">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="8d7d5-257">[要素] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-257">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="8d7d5-258">ドロワー **\(** 下部\) パネルの [アクセシビリティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-258">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="8d7d5-259">[ソース オーダー **ビューアー] セクションで** 、[ソース注文の **表示] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-259">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="8d7d5-260">HTML 要素を強調表示して、ページ ソース内の順序に合ったオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-260">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソース 注文ビューアー" lightbox="../media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="8d7d5-262">**[アクセシビリティ] ウィンドウ** のソース **注文** ビューアー</span><span class="sxs-lookup"><span data-stu-id="8d7d5-262">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <span data-ttu-id="8d7d5-263">キーボード ショートカット エディターを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-263">Enable keyboard shortcut editor</span></span>

<span data-ttu-id="8d7d5-264">キーボード ショートカット **エディターの** 有効化実験を有効にすると、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-264">With the **Enable keyboard shortcut editor** experiment turned on, you are now able to customize keyboard shortcuts for any action in the DevTools.</span></span>  <span data-ttu-id="8d7d5-265">特定の操作のキーボード ショートカットをカスタマイズするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-265">To customize the keyboard shortcut for a specific action, complete the following steps.</span></span>  

1.  <span data-ttu-id="8d7d5-266">[DevTools を開きます][DevtoolsOpenMain]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-266">[Open DevTools][DevtoolsOpenMain].</span></span>  
1.  <span data-ttu-id="8d7d5-267">[設定 [] を開きます][DevToolsCustomizeSettings]。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-267">Open [Settings][DevToolsCustomizeSettings].</span></span>
    *   <span data-ttu-id="8d7d5-268">選択します `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-268">Select `Shift`+`?`.</span></span>  
1.  <span data-ttu-id="8d7d5-269">[ショートカット] **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-269">Navigate to the **Shortcuts** page.</span></span>  
1.  <span data-ttu-id="8d7d5-270">カスタマイズするアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-270">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="8d7d5-271">[ **編集** \( ![ EditKeyboardShortcut \) ] ][ImageEditKeyboardShortcutIcon] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-271">Choose the **Edit** \(![EditKeyboardShortcut][ImageEditKeyboardShortcutIcon]\) icon.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="[設定] の [ショートカット] ページからカスタマイズするアクションを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       <span data-ttu-id="8d7d5-273">[設定] の [ショートカット] ページ **からカスタマイズ** するアクションを選択 [する][DevToolsCustomizeSettings]</span><span class="sxs-lookup"><span data-stu-id="8d7d5-273">Choose the action to customize from the **Shortcuts** page in [Settings][DevToolsCustomizeSettings]</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="8d7d5-274">キーボードで、アクションにバインドするキーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-274">On the keyboard, select the keys you want to bind to the action.</span></span>
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="アクションに割り当てるキーを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="8d7d5-276">アクションに割り当てるキーを選択する</span><span class="sxs-lookup"><span data-stu-id="8d7d5-276">Select the keys you want to assign to the action</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="8d7d5-277">新しいキーボード ショートカットを保存するには、チェックマーク \(</span><span class="sxs-lookup"><span data-stu-id="8d7d5-277">To save your new keyboard shortcut, choose the checkmark \(</span></span>![CheckmarkKeyboardShortcut][ImageCheckmarkKeyboardShortcutIcon]<span data-ttu-id="8d7d5-279">\) アイコン</span><span class="sxs-lookup"><span data-stu-id="8d7d5-279">\) icon.</span></span>
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="チェックマーク アイコンを選択して新しいキーボード ショートカットを保存する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="8d7d5-281">チェックマーク アイコンを選択して新しいキーボード ショートカットを保存する</span><span class="sxs-lookup"><span data-stu-id="8d7d5-281">Choose the checkmark icon to save your new keyboard shortcut</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="8d7d5-282">DevTools でアクションをトリガーするには、新しいキーボード ショートカットを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-282">Select your new keyboard shortcut to trigger the action in the DevTools.</span></span>  
    
<span data-ttu-id="8d7d5-283">[ショートカット **] ページ** で、ユーザー設定のキーボード ショートカット **\(** CustomKeyboardShortcut \) アイコンに、カスタマイズしたキーボード ショートカット ![ ][ImageCustomKeyboardShortcutIcon] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-283">On the **Shortcuts** page, the **Custom Keyboard Shortcut** \(![CustomKeyboardShortcut][ImageCustomKeyboardShortcutIcon]\) icon displays keyboard shortcuts that you have customized.</span></span>  <span data-ttu-id="8d7d5-284">すべてのショートカットをリセットするには、[既定のショートカット **を復元する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-284">To reset all shortcuts, choose **Restore default shortcuts**.</span></span>  

<span data-ttu-id="8d7d5-285">When you are editing the keyboard shortcuts for an action, to discard your changes, choose the X \( ![ XKeyboardShortcut ][ImageXKeyboardShortcutIcon] \) icon.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-285">When you are editing the keyboard shortcuts for an action, to discard your changes, choose the X \(![XKeyboardShortcut][ImageXKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="8d7d5-286">特定のアクションのショートカットを削除するには、ショートカットの **削除** \( ![ DeleteKeyboardShortcut ][ImageDeleteKeyboardShortcutIcon] \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-286">To remove shortcuts for a specific action, choose the **Delete shortcut** \(![DeleteKeyboardShortcut][ImageDeleteKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="8d7d5-287">1 つのアクションに複数のショートカットを追加するには、[ショートカットの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-287">To add multiple shortcuts for an action, choose **Add a shortcut**.</span></span>

> [!NOTE]
> <span data-ttu-id="8d7d5-288">キーボード ショートカットが別のアクションに現在割り当てられている場合は、新しい操作のためにキーボード ショートカットを保存できない。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-288">If a keyboard shortcut is currently assigned to another action, you are not able to save it for a new action.</span></span>  <span data-ttu-id="8d7d5-289">最初に、前の操作のキーボード ショートカットを削除してから、新しいアクションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-289">You must first delete the keyboard shortcut for the previous action and then add it to the new action.</span></span>  

<!--Available in Microsoft Edge version 87 and later.  -->

### <span data-ttu-id="8d7d5-290">3D ビューで複合レイヤーを有効にする</span><span class="sxs-lookup"><span data-stu-id="8d7d5-290">Turn on Composited Layers in 3D View</span></span>

<span data-ttu-id="8d7d5-291">レイヤーを z インデックスとドキュメント オブジェクト モデル \(DOM\) と共に視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-291">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="8d7d5-292">この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-292">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="8d7d5-293">コンテキストの切り替えの削減が大きな問題と見なされました。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-293">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="8d7d5-294">作成するコードが Web アプリに与える影響は必ずしも明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-294">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="8d7d5-295">視覚的なデバッグを総合的に行う目的で、3D ビューレイヤーと複合レイヤーが結合されました。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-295">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  <span data-ttu-id="8d7d5-296">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-296">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="8d7d5-297">複合レイヤー **を使用するには、次**の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-297">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="8d7d5-298">ドロワーで **、3D ビュー ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-298">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="8d7d5-299">[コンポジット **レイヤー] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-299">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="8d7d5-300">アプリのすべての塗り付けレイヤーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-300">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="8d7d5-301">独自の Web アプリでこの機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-301">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="8d7d5-303">**[コンポジット レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="8d7d5-303">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

## <span data-ttu-id="8d7d5-304">以前の試験的な機能</span><span class="sxs-lookup"><span data-stu-id="8d7d5-304">Previous experimental features</span></span>  

*   <span data-ttu-id="8d7d5-305">Microsoft Edge バージョン 83 以降では[、3D][Devtools3dViewIndex]ビューが使用可能になっていて、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-305">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="8d7d5-306">[Microsoft][DevtoolsCustomKeyboardShortcuts] Edge バージョン 86 以降で、キーボード ショートカットのカスタマイズが使用可能で、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-306">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  

## <span data-ttu-id="8d7d5-307">試験的な機能に関するフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="8d7d5-307">Providing feedback on experimental features</span></span>  

<span data-ttu-id="8d7d5-308">Microsoft Edge DevTools 実験、または DevTools に関連するその他の実験に関するフィードバックを提供する。</span><span class="sxs-lookup"><span data-stu-id="8d7d5-308">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="8d7d5-309">DevTools の **[フィードバック** の送信] アイコンを使用してフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="8d7d5-309">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="8d7d5-310">次の時点 [でツイート@EdgeDevTools][TwitterEdgedevtools]</span><span class="sxs-lookup"><span data-stu-id="8d7d5-310">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="8d7d5-312">Microsoft Edge DevTools の **[フィードバックの送信]** アイコン</span><span class="sxs-lookup"><span data-stu-id="8d7d5-312">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageCheckmarkKeyboardShortcutIcon]: ../media/checkmark-keyboard-shortcut-icon.msft.png  
[ImageCustomKeyboardShortcutIcon]: ../media/custom-keyboard-shortcut-icon.msft.png  
[ImageDeleteKeyboardShortcutIcon]: ../media/delete-keyboard-shortcut-icon.msft.png  
[ImageEditKeyboardShortcutIcon]: ../media/edit-keyboard-shortcut-icon.msft.png  
[ImageExperimentalApisIcon]: ../media/experimental-apis-dark-icon.msft.png  
[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ../media/span-dark-icon.msft.png  
[ImageXKeyboardShortcutIcon]: ../media/discard-changes-keyboard-shortcut-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D ビュー | Microsoft Docs"  
[DevToolsCustomizeSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools のデバイス モードでモバイル デバイスをシミュレートする |Microsoft Edge"  
[DevtoolsIssues]: ../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools のキーボード ショートカット |Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス |Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Emulator エミュレーターを取得する |Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Emulator エミュレーターを使用する |Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアント |Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface の一方 |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
