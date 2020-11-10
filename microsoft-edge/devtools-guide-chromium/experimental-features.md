---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/06/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: ddedf62ff27023751c511a7d2e34b6ea14461db5
ms.sourcegitcommit: be42902c404e9f9ac2d661df9c55de3db4d956a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2020
ms.locfileid: "11160368"
---
# <span data-ttu-id="3b51f-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="3b51f-104">Experimental features</span></span>  

<span data-ttu-id="3b51f-105">Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="3b51f-106">各機能がリリースされる前に、テストして [フィードバックを提供](#providing-feedback-on-experimental-features) することができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="3b51f-107">Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="3b51f-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-108">Turn on experimental features</span></span>  

<span data-ttu-id="3b51f-109">Microsoft Edge で \ (またはオフ) の試験的機能を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="3b51f-110">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-110">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="3b51f-111">`Control` + `Shift` + `I` \ (Windows, Linux \) または `Command` + `Option` + `I` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="3b51f-112">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="3b51f-113">[ [設定][DevToolsCustomizeSettings] ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="3b51f-114">を選択し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="3b51f-115">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="3b51f-116">[ **設定** ] ウィンドウの左側で、[ **実験** ] セクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.msft.png":::
       <span data-ttu-id="3b51f-118">DevTools の**設定**での実験の一覧</span><span class="sxs-lookup"><span data-stu-id="3b51f-118">List of experiments in DevTools **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3b51f-119">[ **実験** ] ページで、利用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="3b51f-120">Microsoft Edge DevTools を閉じてからもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-120">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="3b51f-121">実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="3b51f-122">実験的な機能を無効にするには、[ **実験** ] ページを開き、無効にする実験的機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="3b51f-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="3b51f-123">Highlighted experimental features</span></span>  

<span data-ttu-id="3b51f-124">以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="3b51f-125">実験的機能</span><span class="sxs-lookup"><span data-stu-id="3b51f-125">Experimental feature</span></span> | <span data-ttu-id="3b51f-126">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="3b51f-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="3b51f-127">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="3b51f-127">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="3b51f-128">84以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-128">84 or later</span></span> |  
| [<span data-ttu-id="3b51f-129">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-129">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="3b51f-130">85以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-130">85 or later</span></span> |  
| [<span data-ttu-id="3b51f-131">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-131">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="3b51f-132">85以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-132">85 or later</span></span> |  
| [<span data-ttu-id="3b51f-133">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-133">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="3b51f-134">85以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-134">85 or later</span></span> |  
| [<span data-ttu-id="3b51f-135">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-135">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="3b51f-136">85以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-136">85 or later</span></span> |  
| [<span data-ttu-id="3b51f-137">ソースオーダービューアー</span><span class="sxs-lookup"><span data-stu-id="3b51f-137">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="3b51f-138">86以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-138">86 or later</span></span> |  
| [<span data-ttu-id="3b51f-139">キーボードショートカットエディターを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-139">Enable keyboard shortcut editor</span></span>](#enable-keyboard-shortcut-editor) | <span data-ttu-id="3b51f-140">87以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-140">87 or later</span></span> |  
| [<span data-ttu-id="3b51f-141">3D ビューでの合成レイヤーの有効化</span><span class="sxs-lookup"><span data-stu-id="3b51f-141">Turn on Composited Layers in 3D View</span></span>](#turn-on-composited-layers-in-3d-view) | <span data-ttu-id="3b51f-142">87以降</span><span class="sxs-lookup"><span data-stu-id="3b51f-142">87 or later</span></span> |  

### <span data-ttu-id="3b51f-143">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="3b51f-143">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="3b51f-144">Microsoft Edge で2つの新しいデュアル画面と折りたたみ式デバイスをエミュレートするための追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-144">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="3b51f-145">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="3b51f-145">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="3b51f-146">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="3b51f-146">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  

<span data-ttu-id="3b51f-147">デバイスをエミュレートし、次の後処理を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-147">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="3b51f-148">シングルスクリーンまたは折り目</span><span class="sxs-lookup"><span data-stu-id="3b51f-148">single-screen or folded posture</span></span>  
*   <span data-ttu-id="3b51f-149">デュアルスクリーンまたは折る</span><span class="sxs-lookup"><span data-stu-id="3b51f-149">dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="3b51f-150">[実験的な Web Platform api を有効](#enable-experimental-apis) にして、 [CSS メディアの画面スパン機能][DualScreenDocsCssMedia] と [JavaScript getwindowsegments API][DualScreenDocsJSAPI] を使用して、デュアルスクリーンデバイスと折りたたみ式デバイス用の web サイト (またはアプリ) を強化します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-150">[Enable experimental Web Platform APIs](#enable-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="./media/experiments-surface-duo-emulation.msft.png" alt-text="Microsoft Edge で Surface Duo をエミュレートする" lightbox="./media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="3b51f-152">Microsoft Edge で Surface Duo をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="3b51f-152">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="3b51f-153">実験的な Api を有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-153">Enable experimental APIs</span></span>  

<span data-ttu-id="3b51f-154">[CSS メディアの画面スパン機能][DualScreenDocsCssMedia]と[JavaScript GETWINDOWSEGMENTS API][DualScreenDocsJSAPI]を使用するには、 `Experimental Web Platform features` Microsoft Edge でフラグをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-154">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="3b51f-155">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-155">Complete the following steps.</span></span>  

1.  <span data-ttu-id="3b51f-156">に移動 `edge://flags` します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-156">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="3b51f-157">[ **検索フラグ** ] ボックスに、「 `Experimental Web Platform features` 実験的な **Web Platform 機能** 」というフラグを選択して、[ **無効** ] を [ **有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-157">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="3b51f-158">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="3b51f-158">Restart Microsoft Edge.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="実験的な Web Platform 機能のフラグを有効にする" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="3b51f-160">実験的な Web Platform 機能のフラグを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-160">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="3b51f-161">[CSS メディアクエリ][DualScreenDocsCssMedia]または[JavaScript WINDOWS セグメント列挙 API][DualScreenDocsJSAPI]を使用して[surface duo][SurfaceDevicesDuo]の web サイトまたはアプリを強化する場合は、 [Surface duo][SurfaceDevicesDuo]デバイス上の[Android Microsoft Edge アプリ][GooglePlayMicrosoftEdge]の試用版の**Web プラットフォーム機能**フラグも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-161">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="3b51f-162">[デスクトップ][MicrosoftEdge]microsoft Edge で**実験的な Web Platform 機能**のフラグが有効になっていて、 [android microsoft edge アプリ][GooglePlayMicrosoftEdge]で無効になっている場合、デスクトップ microsoft edge の surface duo エミュレーターの web サイトまたはアプリの動作は[surface duo][SurfaceDevicesDuo]の[Android microsoft edge アプリ][GooglePlayMicrosoftEdge]と一致しません。</span><span class="sxs-lookup"><span data-stu-id="3b51f-162">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="3b51f-163">[デスクトップ Microsoft edge][MicrosoftEdge]で Surface Duo エミュレーターを正常に使用するために、Android とデスクトップの microsoft edge の間でフラグが一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-163">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="3b51f-164">折りたたみ式とデュアルスクリーンデバイスでのテスト</span><span class="sxs-lookup"><span data-stu-id="3b51f-164">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="3b51f-165">Microsoft Edge のデュアル画面の姿勢で [Surface Duo][SurfaceDevicesDuo] をエミュレートすると、ユーザーの web サイトまたはアプリ上で、継ぎ目 (2 つの画面間のスペース) が描画されます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-165">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="3b51f-166">エミュレートされたディスプレイは、 [Surface Duo][SurfaceDevicesDuo]で実行されている[Microsoft Edge Android アプリ][GooglePlayMicrosoftEdge]での web サイト \ (またはアプリ \) の表示方法と一致します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-166">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] running on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="3b51f-167">お客様の web サイト \ (またはアプリ \) を更新して、継ぎ目に合わせて表示を改善しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-167">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="3b51f-168">Web サイトの外観 (またはアプリ \) を seam に適合させる方法については、「 [seam の操作方法][DualScreenIntroductionHowWorkSeam]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-168">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam].</span></span>  

<span data-ttu-id="3b51f-169">[デバイスツールバー][DevtoolsDeviceModeIndexSimulateMobileViewport]には、web サイトまたはアプリを複数の方法でテストするための追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3b51f-169">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="3b51f-170">**Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 \ (回転 \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-170">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="3b51f-171">この機能を **スパン** \ ( ![ スパン \) と組み合わせると、シングル画面で、または折る、または折り目を切り替えることが ][ImageSpanIcon] できます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-171">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="3b51f-172">これらの機能により、web サイトやアプリを4つのすべての方法でテストできます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-172">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="3b51f-174">デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス</span><span class="sxs-lookup"><span data-stu-id="3b51f-174">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="3b51f-175">**実験的な Web platform 機能**\ ( ![ ExperimentalApis ][ImageExperimentalApisIcon] \) アイコンは、**実験的な web プラットフォーム機能**のフラグの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-175">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="3b51f-176">フラグがオンになっている場合は、アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-176">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="3b51f-177">フラグがオフになっている場合、アイコンは強調表示されません。</span><span class="sxs-lookup"><span data-stu-id="3b51f-177">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="3b51f-178">フラグをオン (またはオフ) にするには、フラグに移動 `edge://flags` して切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-178">To turn on \(or off\) the flag, navigate to `edge://flags` and toggle the flag.</span></span>  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

<span data-ttu-id="3b51f-179">ここでは、デュアルスクリーンデバイス向けの web サイト (またはアプリ) を強化するために役立つその他のリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-179">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices.</span></span>  

*   <span data-ttu-id="3b51f-180">デュアルスクリーンデバイスでの web 開発の詳細については、「 [デュアルスクリーン web エクスペリエンス][DualScreenWebIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-180">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="3b51f-181">[Surface Duo エミュレーター][DualScreenAndroidUseEmulator]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-181">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="3b51f-182">これは、Microsoft Edge のエミュレーターとは異なり、Android を実行している Surface Duo のエミュレートと [Android Studio][AndroidDeveloperStudio]との統合です。</span><span class="sxs-lookup"><span data-stu-id="3b51f-182">It is different from the emulator in Microsoft Edge, emulates the Surface Duo running Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="3b51f-183">詳細については、「 [Surface DUO SDK の入手][DualScreenAndroidGetDuoSdk]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-183">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

> [!NOTE]
> <span data-ttu-id="3b51f-184">次に、現在の既知の問題の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-184">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="3b51f-185">[Microsoft リモートデスクトップクライアント][RemoteDesktopClientDocs]を使ってリモート PC に接続し、 [Surface Duo][SurfaceDevicesDuo]または[Samsung Galaxy の折りたたみ][SamsungMobileGalaxyFold]をエミュレートすると、ポインターがシェイクまたは途切れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-185">When using a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="3b51f-186">この問題が発生した場合は、 [フィードバックを送信](#providing-feedback-on-experimental-features)してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-186">If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).</span></span>  

### <span data-ttu-id="3b51f-187">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-187">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="3b51f-188">この実験的な機能には、CSS グリッドレイアウトのデバッグに役立つ多くの新しい視覚エフェクトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3b51f-188">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="3b51f-189">最新の実験的な機能をプレビューするには、 [この実験を有効に](#turn-on-experimental-features) して、devtools を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-189">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="3b51f-190">この実験は、Microsoft Edge バージョン87以降では既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="3b51f-190">This experiment is on by default in Microsoft Edge version 87 or later.</span></span>  

#### <span data-ttu-id="3b51f-191">検査ツールを使用したホバーグリッドのオーバーレイの表示</span><span class="sxs-lookup"><span data-stu-id="3b51f-191">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="3b51f-192">**検査**ツールを使うと、マウスをポイントして web サイトの CSS グリッドのレイアウトを簡単に識別して視覚化することができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-192">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="3b51f-193">**Inspect** ![ ](./media/inspect-icon.msft.png) Devtools の左上隅にある検査 (検査 \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-193">Choose the **Inspect** \(![Inspect](./media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="3b51f-194">次に、デバッグしている web サイトの Grid 要素にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-194">Then, hover over a Grid element on the website you are debugging.</span></span>  <span data-ttu-id="3b51f-195">グリッドの周りに枠線が表示され、[網かけ] ではグリッドのギャップの位置が示されます (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="3b51f-195">Outlines are displayed around the grid, and shading indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="./media/grid-inspect.msft.png" alt-text="検査ツールでグリッドを表示する" lightbox="./media/grid-inspect.msft.png":::
   <span data-ttu-id="3b51f-197">検査ツールでグリッドを表示する</span><span class="sxs-lookup"><span data-stu-id="3b51f-197">Viewing grids with the Inspect tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="3b51f-198">永続的なグリッドのオーバーレイの表示</span><span class="sxs-lookup"><span data-stu-id="3b51f-198">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="3b51f-199">Microsoft Edge バージョン86以降では、実験的な CSS grid 機能で、持続的な Grid オーバーレイを有効にするオプションも提供されています。</span><span class="sxs-lookup"><span data-stu-id="3b51f-199">In Microsoft Edge version 86 or later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="3b51f-200">永続的なオーバーレイにはいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-200">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="3b51f-201">永続的なオーバーレイはスクロールしてもページに表示されたままになり、マウスを動かすと、DevTools のその他の機能を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-201">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="3b51f-202">同時に複数の持続的なオーバーレイを有効にすることができます。複数のグリッドレイアウトを一度に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-202">Multiple persistent overlays can be enabled at the same time, allowing you to review several grid layouts at once.</span></span>  
*   <span data-ttu-id="3b51f-203">永続的なオーバーレイには、グリッド領域の名前の非表示と表示、グリッドのギャップ、追跡サイズなど、さまざまな構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3b51f-203">Persistent overlays offer many configuration options, such as hiding or showing names in the grid area, grid gaps, track sizes, and so on.</span></span>  

<span data-ttu-id="3b51f-204">永続的なグリッドのオーバーレイを切り替える2つの方法</span><span class="sxs-lookup"><span data-stu-id="3b51f-204">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="3b51f-205">**要素**ツールの DOM ツリーに表示されている grid 要素の隣にある**グリッド**楕円アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-205">Choose the **Grid** oval icon next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="./media/grid-adorner.msft.png" alt-text="要素ツールのグリッドの [楕円] アイコン" lightbox="./media/grid-adorner.msft.png":::
       <span data-ttu-id="3b51f-207">**要素**ツールのグリッドの [楕円] アイコン</span><span class="sxs-lookup"><span data-stu-id="3b51f-207">Grid oval icon in **Elements** tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="3b51f-208">[要素] ツールにある新しい **レイアウト** パネルを開き、強調表示する各グリッド要素の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-208">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="./media/grid-layout-zoom.msft.png" alt-text="DevTools のレイアウトパネル" lightbox="./media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="3b51f-210">DevTools の**レイアウト**パネル</span><span class="sxs-lookup"><span data-stu-id="3b51f-210">**Layout** panel in DevTools</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="3b51f-211">永続的なオーバーレイの構成</span><span class="sxs-lookup"><span data-stu-id="3b51f-211">Configuring persistent overlays</span></span>  

<span data-ttu-id="3b51f-212">Microsoft Edge バージョン86以降では、新しい **レイアウト** パネルは **要素** ツールの [ **スタイル** ] タブと [ **計算** ] タブにあります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-212">In Microsoft Edge version 86 or later, the new **Layout** panel is located in the **Elements** tool alongside the **Styles** and **Computed** tabs.</span></span>  <span data-ttu-id="3b51f-213">**レイアウト**パネルには、持続的なオーバーレイの構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-213">The **Layout** panel surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.msft.png":::
   <span data-ttu-id="3b51f-215">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="3b51f-215">CSS grid debugging feature</span></span>  
:::image-end:::  

### <span data-ttu-id="3b51f-216">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-216">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="3b51f-217">通常、 **要素** や **ネットワーク** などのツールは、devtools の上部にあるメインパネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-217">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="3b51f-218">**3D ビュー**などのツール、および devtools の下部にある**引き出し**パネルで通常のみ開かれる**問題**。</span><span class="sxs-lookup"><span data-stu-id="3b51f-218">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="3b51f-219">実験を選択した後、上下のパネル間でツールを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-219">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="3b51f-220">ツールを移動するには、タブの上にマウスポインターを合わせて、コンテキストメニューの [ **先頭へ移動** ] または [ **下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-220">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="3b51f-221">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-221">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="3b51f-222">**ドロワー**パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-222">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.msft.png":::
   <span data-ttu-id="3b51f-224">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="3b51f-224">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="3b51f-225">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-225">Enable webhint</span></span>  

<span data-ttu-id="3b51f-226">[webhint][WebhintMain] は、web サイトやローカル web ページにリアルタイムでフィードバックを提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="3b51f-226">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="3b51f-227">[Webhint][WebhintMain]によって提供されるフィードバックの種類。</span><span class="sxs-lookup"><span data-stu-id="3b51f-227">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="3b51f-228">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="3b51f-228">accessibility</span></span>  
*   <span data-ttu-id="3b51f-229">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="3b51f-229">cross-browser compatibility</span></span>  
*   <span data-ttu-id="3b51f-230">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3b51f-230">security</span></span>  
*   <span data-ttu-id="3b51f-231">処理</span><span class="sxs-lookup"><span data-stu-id="3b51f-231">performance</span></span>  
*   <span data-ttu-id="3b51f-232">プログレッシブ Web アプリ (PWAs)</span><span class="sxs-lookup"><span data-stu-id="3b51f-232">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="3b51f-233">その他の一般的な web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="3b51f-233">other common web development issues</span></span>  

<span data-ttu-id="3b51f-234">[Webhint][WebhintMain]の実験では、[[問題][DevtoolsIssues]] パネルに webhint のフィードバックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-234">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="3b51f-235">問題を選択すると、ソリューションのドキュメントと web サイト上の影響を受けるリソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-235">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="3b51f-236">リソースリンクを選んで、DevTools で関連する **ネットワーク**、 **ソース**、または **要素** のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-236">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.msft.png":::
   <span data-ttu-id="3b51f-238">[ **問題** ] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="3b51f-238">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="3b51f-239">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-239">Enable Network Console</span></span>  

<span data-ttu-id="3b51f-240">**ネットワーク本体** は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="3b51f-240">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="3b51f-241">**ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-241">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="3b51f-242">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-242">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="3b51f-243">**ネットワークコンソール**を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-243">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="3b51f-244">[ **ネットワーク** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-244">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="3b51f-245">変更して再送信するネットワーク要求を見つけます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-245">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="3b51f-246">コンテキストメニューを開き (\ 右クリック \)、[ **編集と再生**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-246">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="3b51f-247">**ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-247">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="3b51f-248">[ **送信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-248">Choose **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="Console ドローワのネットワーク本体" lightbox="./media/network-network-console.msft.png":::
   <span data-ttu-id="3b51f-250">**Console**ドローワの**ネットワーク本体**</span><span class="sxs-lookup"><span data-stu-id="3b51f-250">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="3b51f-251">ソースオーダービューアー</span><span class="sxs-lookup"><span data-stu-id="3b51f-251">Source Order Viewer</span></span>  

<span data-ttu-id="3b51f-252">**ソースオーダービューアー** は、ページソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="3b51f-252">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="3b51f-253">オンスクリーン表示の順序は、ソースの順序とは異なる場合があります。これには、スクリーンリーダーとキーボードのユーザーが混乱させるます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-253">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="3b51f-254">**ソース注文ビューアー**を使用して、画面上の表示順序とソースの順序の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-254">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="3b51f-255">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-255">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="3b51f-256">**ソースオーダービューアー**を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-256">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="3b51f-257">[ **要素** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="3b51f-257">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="3b51f-258">[引き出し] \ (下) パネルで [ **アクセシビリティ** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-258">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="3b51f-259">[ **ソース注文ビューアー** ] セクションで、[ **ソースの順序を表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3b51f-259">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="3b51f-260">任意の HTML 要素を強調表示して、ページソースの順序でオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-260">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソースオーダービューアー" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="3b51f-262">[**アクセシビリティ**] ウィンドウの**ソースオーダービューアー**</span><span class="sxs-lookup"><span data-stu-id="3b51f-262">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <span data-ttu-id="3b51f-263">キーボードショートカットエディターを有効にする</span><span class="sxs-lookup"><span data-stu-id="3b51f-263">Enable keyboard shortcut editor</span></span>

<span data-ttu-id="3b51f-264">[ **キーボードショートカットを有効にする** ] をオンにすると、devtools で操作のキーボードショートカットをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3b51f-264">With the **Enable keyboard shortcut editor** experiment turned on, you are now able to customize keyboard shortcuts for any action in the DevTools.</span></span>  <span data-ttu-id="3b51f-265">特定のアクションのキーボードショートカットをカスタマイズするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-265">To customize the keyboard shortcut for a specific action, complete the following steps.</span></span>  

1.  <span data-ttu-id="3b51f-266">[DevTools を開き][DevtoolsOpenMain]ます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-266">[Open DevTools][DevtoolsOpenMain].</span></span>  
1.  <span data-ttu-id="3b51f-267">[ [設定][DevToolsCustomizeSettings]] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-267">Open [Settings][DevToolsCustomizeSettings].</span></span>
    *   <span data-ttu-id="3b51f-268">を選択し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-268">Select `Shift`+`?`.</span></span>  
1.  <span data-ttu-id="3b51f-269">[ **ショートカット** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-269">Navigate to the **Shortcuts** page.</span></span>  
1.  <span data-ttu-id="3b51f-270">カスタマイズするアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-270">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="3b51f-271">[ **Edit** ![ ] (edit キーボードショートカット ][ImageEditKeyboardShortcutIcon] ) アイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-271">Choose the **Edit** \(![EditKeyboardShortcut][ImageEditKeyboardShortcutIcon]\) icon.</span></span>  
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="[設定] の [ショートカット] ページからカスタマイズするアクションを選ぶ" lightbox="./media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       <span data-ttu-id="3b51f-273">[[設定][DevToolsCustomizeSettings]] の [**ショートカット**] ページからカスタマイズするアクションを選ぶ</span><span class="sxs-lookup"><span data-stu-id="3b51f-273">Choose the action to customize from the **Shortcuts** page in [Settings][DevToolsCustomizeSettings]</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="3b51f-274">キーボードで、アクションにバインドするキーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-274">On the keyboard, select the keys you want to bind to the action.</span></span>
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="アクションに割り当てるキーを選択します。" lightbox="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="3b51f-276">アクションに割り当てるキーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-276">Select the keys you want to assign to the action</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="3b51f-277">新しいキーボードショートカットを保存するには、チェックマークを選択します (</span><span class="sxs-lookup"><span data-stu-id="3b51f-277">To save your new keyboard shortcut, choose the checkmark \(</span></span>![ショートカットキーのマーク][ImageCheckmarkKeyboardShortcutIcon]<span data-ttu-id="3b51f-279">\) アイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-279">\) icon.</span></span>
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="新しいキーボードショートカットを保存するには、チェックマークアイコンを選択します。" lightbox="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="3b51f-281">新しいキーボードショートカットを保存するには、チェックマークアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-281">Choose the checkmark icon to save your new keyboard shortcut</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="3b51f-282">新しいキーボードショートカットを選択して、DevTools で操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-282">Select your new keyboard shortcut to trigger the action in the DevTools.</span></span>  
    
<span data-ttu-id="3b51f-283">[ **ショートカット** ] ページでは、 **カスタムキーボードショートカット** ( ![ customkeyboard shortcut ][ImageCustomKeyboardShortcutIcon] \) アイコンに、カスタマイズしたショートカットキーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-283">On the **Shortcuts** page, the **Custom Keyboard Shortcut** \(![CustomKeyboardShortcut][ImageCustomKeyboardShortcutIcon]\) icon displays keyboard shortcuts that you have customized.</span></span>  <span data-ttu-id="3b51f-284">すべてのショートカットをリセットするには、[ **既定のショートカットを復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-284">To reset all shortcuts, choose **Restore default shortcuts**.</span></span>  

<span data-ttu-id="3b51f-285">操作のショートカットキーを編集しているときに、変更内容を破棄するには、[X \ ( ![ xkeyboard shortcut ][ImageXKeyboardShortcutIcon] ])] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-285">When you are editing the keyboard shortcuts for an action, to discard your changes, choose the X \(![XKeyboardShortcut][ImageXKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="3b51f-286">特定のアクションのショートカットを削除するには、[ **ショートカットの削除** \ (削除 ![ ][ImageDeleteKeyboardShortcutIcon] )] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-286">To remove shortcuts for a specific action, choose the **Delete shortcut** \(![DeleteKeyboardShortcut][ImageDeleteKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="3b51f-287">アクションの複数のショートカットを追加するには、[ **ショートカットの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-287">To add multiple shortcuts for an action, choose **Add a shortcut**.</span></span>

> [!NOTE]
> <span data-ttu-id="3b51f-288">キーボードショートカットが現在別のアクションに割り当てられている場合、新しいアクションに保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b51f-288">If a keyboard shortcut is currently assigned to another action, you are not able to save it for a new action.</span></span>  <span data-ttu-id="3b51f-289">最初に、前のアクションのショートカットキーを削除してから、新しいアクションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b51f-289">You must first delete the keyboard shortcut for the previous action and then add it to the new action.</span></span>  

<!--Available in Microsoft Edge version 87 and later.  -->

### <span data-ttu-id="3b51f-290">3D ビューでの合成レイヤーの有効化</span><span class="sxs-lookup"><span data-stu-id="3b51f-290">Turn on Composited Layers in 3D View</span></span>

<span data-ttu-id="3b51f-291">これで、z インデックスとドキュメントオブジェクトモデル \ (DOM \) のレイヤーを視覚化することができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-291">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="3b51f-292">この機能を使うと、頻繁にコンテキストを切り替えることなく、デバッグを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-292">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="3b51f-293">コンテキスト切り替えの削減が重大な問題点であったことを特定しました。</span><span class="sxs-lookup"><span data-stu-id="3b51f-293">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="3b51f-294">入力するコードが web アプリにどのように影響するかは必ずしも明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="3b51f-294">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="3b51f-295">包括的なビジュアルデバッグエクスペリエンスを実現するために、3D ビューレイヤーと合成レイヤーが結合されました。</span><span class="sxs-lookup"><span data-stu-id="3b51f-295">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  <span data-ttu-id="3b51f-296">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-296">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="3b51f-297">**合成レイヤー**を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-297">To use **Composited Layers**, complete the following steps.</span></span>  

<!--1.  Navigate to a PWA-enabled website such as `twitter.com`.  
1.  Choose the **Install ...** \(![Install PWA icon](./media/install-pwa-icon.msft.png)\) icon to install the Twitter PWA.  If it is already set up, open the app as usual.  
1.  Open the Devtools.  -->  
1.  <span data-ttu-id="3b51f-298">ドロワーで、 **3D ビュー** ツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-298">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="3b51f-299">[ **合成レイヤー** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="3b51f-299">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="3b51f-300">アプリのペイントレイヤーがすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b51f-300">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="3b51f-301">独自の web アプリでこの機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="3b51f-301">Try this feature with your own web apps.</span></span>  

:::image type="complex" source="./media/experiments-layers.msft.png" alt-text="合成レイヤーウィンドウ" lightbox="./media/experiments-layers.msft.png":::
   <span data-ttu-id="3b51f-303">**合成レイヤー** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3b51f-303">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

## <span data-ttu-id="3b51f-304">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="3b51f-304">Previous experimental features</span></span>  

*   <span data-ttu-id="3b51f-305">Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="3b51f-305">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="3b51f-306">Microsoft Edge バージョン86以降では、[ショートカット][DevtoolsCustomKeyboardShortcuts]キーをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3b51f-306">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  

## <span data-ttu-id="3b51f-307">実験的な機能についてフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="3b51f-307">Providing feedback on experimental features</span></span>  

<span data-ttu-id="3b51f-308">Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="3b51f-308">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="3b51f-309">DevTools のフィードバックの **送信** アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="3b51f-309">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="3b51f-310">[@EdgeDevTools][TwitterEdgedevtools]ツイート</span><span class="sxs-lookup"><span data-stu-id="3b51f-310">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="3b51f-312">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="3b51f-312">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageRotateIcon]: ./media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ./media/span-dark-icon.msft.png  
[ImageExperimentalApisIcon]: ./media/experimental-apis-dark-icon.msft.png  
[ImageEditKeyboardShortcutIcon]: ./media/edit-keyboard-shortcut-icon.msft.png  
[ImageCheckmarkKeyboardShortcutIcon]: ./media/checkmark-keyboard-shortcut-icon.msft.png  
[ImageCustomKeyboardShortcutIcon]: ./media/custom-keyboard-shortcut-icon.msft.png  
[ImageDeleteKeyboardShortcutIcon]: ./media/delete-keyboard-shortcut-icon.msft.png  
[ImageXKeyboardShortcutIcon]: ./media/discard-changes-keyboard-shortcut-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D ビュー |Microsoft ドキュメント"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ./device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools でデバイスモードを使ってモバイルデバイスをシミュレートする |Microsoft Edge"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"  
[DevtoolsOpenMain]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン web エクスペリエンス |Microsoft ドキュメント"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo エミュレーターの入手 |Microsoft ドキュメント"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "Seam の操作方法-デュアルスクリーンデバイスの概要 |Microsoft ドキュメント"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用する |Microsoft ドキュメント"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "CSS メディア画面のスパン機能で、デュアルスクリーン検出Microsoft ドキュメント"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーンデバイス用の getWindowSegments JavaScript API |Microsoft ドキュメント"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモートデスクトップクライアント |Microsoft ドキュメント"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy 折りたたみ |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "web ヒント"  
