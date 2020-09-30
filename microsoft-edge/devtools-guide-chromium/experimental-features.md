---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: ae2058ad2beb2d8d3b19061e0935b92173392f23
ms.sourcegitcommit: c24884cc154d6c4809e05ae37d170cb674c408b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091532"
---
# <span data-ttu-id="4f0bc-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="4f0bc-104">Experimental features</span></span>  

<span data-ttu-id="4f0bc-105">Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="4f0bc-106">各機能がリリースされる前に、テストして、[フィードバックを提供](#providing-feedback-on-experimental-features) することができます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-106">You may test and p[provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="4f0bc-107">Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="4f0bc-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-108">Turn on experimental features</span></span>  

<span data-ttu-id="4f0bc-109">Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-109">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="4f0bc-110">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-110">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="4f0bc-111">[ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-111">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="4f0bc-112">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="4f0bc-113">[ [設定][DevToolsCustomizeSettings] ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="4f0bc-114">を選択し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="4f0bc-115">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="4f0bc-116">[ **設定** ] ウィンドウの左側で、[ **実験** ] セクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.msft.png":::
       <span data-ttu-id="4f0bc-118">DevTools の設定での実験の一覧</span><span class="sxs-lookup"><span data-stu-id="4f0bc-118">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4f0bc-119">[ **実験** ] ページで、利用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="4f0bc-120">Microsoft Edge DevTools を閉じてからもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-120">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="4f0bc-121">実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="4f0bc-122">実験的な機能を無効にするには、[ **実験** ] ページを開き、無効にする実験的機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="4f0bc-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="4f0bc-123">Highlighted experimental features</span></span>  

<span data-ttu-id="4f0bc-124">以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="4f0bc-125">実験的機能</span><span class="sxs-lookup"><span data-stu-id="4f0bc-125">Experimental feature</span></span> | <span data-ttu-id="4f0bc-126">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="4f0bc-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="4f0bc-127">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="4f0bc-127">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="4f0bc-128">84以降</span><span class="sxs-lookup"><span data-stu-id="4f0bc-128">84 or later</span></span> |  
| [<span data-ttu-id="4f0bc-129">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-129">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="4f0bc-130">85以降</span><span class="sxs-lookup"><span data-stu-id="4f0bc-130">85 or later</span></span> |  
| [<span data-ttu-id="4f0bc-131">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-131">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="4f0bc-132">85以降</span><span class="sxs-lookup"><span data-stu-id="4f0bc-132">85 or later</span></span> |  
| [<span data-ttu-id="4f0bc-133">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-133">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="4f0bc-134">85以降</span><span class="sxs-lookup"><span data-stu-id="4f0bc-134">85 or later</span></span> |  
| [<span data-ttu-id="4f0bc-135">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-135">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="4f0bc-136">85以降</span><span class="sxs-lookup"><span data-stu-id="4f0bc-136">85 or later</span></span> |  
| [<span data-ttu-id="4f0bc-137">ソースオーダービューアー</span><span class="sxs-lookup"><span data-stu-id="4f0bc-137">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="4f0bc-138">86以降</span><span class="sxs-lookup"><span data-stu-id="4f0bc-138">86 or later</span></span> |  

### <span data-ttu-id="4f0bc-139">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="4f0bc-139">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="4f0bc-140">Microsoft Edge で2つの新しいデュアル画面と折りたたみ式デバイスをエミュレートするための追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-140">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="4f0bc-141">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="4f0bc-141">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="4f0bc-142">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="4f0bc-142">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  

<span data-ttu-id="4f0bc-143">デバイスをエミュレートし、次の後処理を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-143">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="4f0bc-144">シングルスクリーンまたは折り目</span><span class="sxs-lookup"><span data-stu-id="4f0bc-144">single-screen or folded posture</span></span>  
*   <span data-ttu-id="4f0bc-145">デュアルスクリーンまたは折る</span><span class="sxs-lookup"><span data-stu-id="4f0bc-145">dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="4f0bc-146">[実験的な Web Platform api を有効](#enable-experimental-apis) にして、 [CSS メディアの画面スパン機能][DualScreenDocsCssMedia] と [JavaScript getwindowsegments API][DualScreenDocsJSAPI] を使用して、デュアルスクリーンデバイスと折りたたみ式デバイス用の web サイト (またはアプリ) を強化します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-146">[Enable experimental Web Platform APIs](#enable-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="./media/experiments-surface-duo-emulation.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="4f0bc-148">Microsoft Edge で Surface Duo をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-148">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="4f0bc-149">実験的な Api を有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-149">Enable experimental APIs</span></span>  

<span data-ttu-id="4f0bc-150">[CSS メディアの画面スパン機能][DualScreenDocsCssMedia]と[JavaScript GETWINDOWSEGMENTS API][DualScreenDocsJSAPI]を使用するには、 `Experimental Web Platform features` Microsoft Edge でフラグをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-150">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="4f0bc-151">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-151">Complete the following steps.</span></span>  

1.  <span data-ttu-id="4f0bc-152">に移動 `edge://flags` します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-152">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="4f0bc-153">[ **検索フラグ** ] ボックスに、「 `Experimental Web Platform features` 実験的な **Web Platform 機能** 」というフラグを選択して、[ **無効** ] を [ **有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-153">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="4f0bc-154">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-154">Restart Microsoft Edge.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="4f0bc-156">実験的な Web Platform 機能のフラグを有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-156">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="4f0bc-157">[CSS メディアクエリ][DualScreenDocsCssMedia]または[JavaScript WINDOWS セグメント列挙 API][DualScreenDocsJSAPI]を使用して[surface duo][SurfaceDevicesDuo]の web サイトまたはアプリを強化する場合は、 [Surface duo][SurfaceDevicesDuo]デバイス上の[Android Microsoft Edge アプリ][GooglePlayMicrosoftEdge]の試用版の**Web プラットフォーム機能**フラグも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-157">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="4f0bc-158">[デスクトップ][MicrosoftEdge]microsoft Edge で**実験的な Web Platform 機能**のフラグが有効になっていて、 [android microsoft edge アプリ][GooglePlayMicrosoftEdge]で無効になっている場合、デスクトップ microsoft edge の surface duo エミュレーターの web サイトまたはアプリの動作は[surface duo][SurfaceDevicesDuo]の[Android microsoft edge アプリ][GooglePlayMicrosoftEdge]と一致しません。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-158">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="4f0bc-159">[デスクトップ Microsoft edge][MicrosoftEdge]で Surface Duo エミュレーターを正常に使用するために、Android とデスクトップの microsoft edge の間でフラグが一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-159">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="4f0bc-160">折りたたみ式とデュアルスクリーンデバイスでのテスト</span><span class="sxs-lookup"><span data-stu-id="4f0bc-160">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="4f0bc-161">Microsoft Edge のデュアル画面の姿勢で [Surface Duo][SurfaceDevicesDuo] をエミュレートすると、ユーザーの web サイトまたはアプリ上で、継ぎ目 (2 つの画面間のスペース) が描画されます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-161">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="4f0bc-162">エミュレートされたディスプレイは、web サイト \ (またはアプリ \) と[Surface Duo][SurfaceDevicesDuo]の[Microsoft Edge Android アプリ][GooglePlayMicrosoftEdge]での表示方法に一致します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-162">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="4f0bc-163">お客様の web サイト \ (またはアプリ \) を更新して、継ぎ目に合わせて表示を改善しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-163">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="4f0bc-164">Web サイトの外観を seam に適合させる方法の詳細については、Surface Duo のドキュメントで [seam を操作する方法][DualScreenIntroductionHowWorkSeam] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-164">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam] in the Surface Duo documentation.</span></span>  

<span data-ttu-id="4f0bc-165">[デバイスツールバー][DevtoolsDeviceModeIndexSimulateMobileViewport]には、web サイトまたはアプリを複数の方法でテストするための追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-165">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="4f0bc-166">**Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 \ (回転 \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-166">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="4f0bc-167">この機能を **スパン** \ ( ![ スパン \) と組み合わせると、シングル画面で、または折る、または折り目を切り替えることが ][ImageSpanIcon] できます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-167">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="4f0bc-168">これらの機能により、web サイトやアプリを4つのすべての方法でテストできます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-168">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="4f0bc-170">デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス</span><span class="sxs-lookup"><span data-stu-id="4f0bc-170">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="4f0bc-171">**実験的な Web platform 機能**\ ( ![ ExperimentalApis ][ImageExperimentalApisIcon] \) アイコンは、**実験的な web プラットフォーム機能**のフラグの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-171">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="4f0bc-172">フラグがオンになっている場合は、アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-172">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="4f0bc-173">フラグがオフになっている場合、アイコンは強調表示されません。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-173">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="4f0bc-174">フラグをオン (またはオフ) にするには、フラグに移動 `edge://flags` して切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-174">To turn on \(or off\) the flag, navigate to `edge://flags` and toggle the flag.</span></span>  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

<span data-ttu-id="4f0bc-175">ここでは、デュアルスクリーンデバイス向けの web サイト (またはアプリ) を強化するために役立つその他のリソースを紹介します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-175">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices:</span></span>
*   <span data-ttu-id="4f0bc-176">デュアルスクリーンデバイスでの web 開発の詳細については、「 [デュアルスクリーン web エクスペリエンス][DualScreenWebIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-176">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="4f0bc-177">[Surface Duo エミュレーター][DualScreenAndroidUseEmulator]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-177">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="4f0bc-178">これは、Microsoft Edge のエミュレーターとは異なり、Android を実行している Surface Duo のエミュレートと [Android Studio][AndroidDeveloperStudio]との統合です。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-178">It is different from the emulator in Microsoft Edge, emulates the Surface Duo running Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="4f0bc-179">詳細については、「 [Surface DUO SDK の入手][DualScreenAndroidGetDuoSdk]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-179">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

> [!NOTE]
> <span data-ttu-id="4f0bc-180">次に、現在の既知の問題の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-180">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="4f0bc-181">[Microsoft リモートデスクトップクライアント][RemoteDesktopClientDocs]を使ってリモート PC に接続し、 [Surface Duo][SurfaceDevicesDuo]または[Samsung Galaxy の折りたたみ][SamsungMobileGalaxyFold]をエミュレートすると、ポインターがシェイクまたは途切れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-181">When using a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="4f0bc-182">この問題が発生した場合は、 [フィードバックを送信](#providing-feedback-on-experimental-features)してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-182">If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).</span></span>  

### <span data-ttu-id="4f0bc-183">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-183">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="4f0bc-184">この実験的な機能には、CSS グリッドレイアウトのデバッグに役立つ多くの新しい視覚エフェクトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-184">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="4f0bc-185">最新の実験的な機能をプレビューするには、 [この実験を有効に](#turn-on-experimental-features) して、devtools を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-185">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="4f0bc-186">この実験は、Edge 87 以降では既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-186">This experiment is on by default in Edge 87 and later.</span></span>  

#### <span data-ttu-id="4f0bc-187">検査ツールを使用したホバーグリッドのオーバーレイの表示</span><span class="sxs-lookup"><span data-stu-id="4f0bc-187">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="4f0bc-188">**検査**ツールを使うと、マウスをポイントして web サイトの CSS グリッドのレイアウトを簡単に識別して視覚化することができます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-188">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="4f0bc-189">**Inspect** ![ ](./media/inspect-icon.msft.png) Devtools の左上隅にある検査 (検査 \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-189">Choose the **Inspect** \(![Inspect](./media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="4f0bc-190">次に、デバッグしている web サイトの Grid 要素にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-190">Then, hover over a Grid element on the website you are debugging.</span></span>  <span data-ttu-id="4f0bc-191">グリッドの周りに枠線が表示され、[網かけ] ではグリッドのギャップの位置が示されます (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-191">Outlines are displayed around the grid, and shading indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="./media/grid-inspect.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/grid-inspect.msft.png":::
   <span data-ttu-id="4f0bc-193">検査ツールでグリッドを表示する</span><span class="sxs-lookup"><span data-stu-id="4f0bc-193">Viewing grids with the Inspect tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="4f0bc-194">永続的なグリッドのオーバーレイの表示</span><span class="sxs-lookup"><span data-stu-id="4f0bc-194">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="4f0bc-195">Edge 86 以降では、実験的な CSS grid 機能で、持続的なグリッドのオーバーレイを有効にするオプションも提供されています。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-195">In Edge 86 and later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="4f0bc-196">永続的なオーバーレイにはいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-196">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="4f0bc-197">永続的なオーバーレイはスクロールしてもページに表示されたままになり、マウスを動かすと、DevTools のその他の機能を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-197">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="4f0bc-198">同時に複数の持続的なオーバーレイを有効にすることができます。複数のグリッドレイアウトを一度に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-198">Multiple persistent overlays can be enabled at the same time, allowing you to review numerous grid layouts at once.</span></span>  
*   <span data-ttu-id="4f0bc-199">永続的なオーバーレイには、グリッド領域名の非表示または表示、グリッドのギャップ、トラックサイズなど、さまざまな構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-199">Persistent overlays offer many configuration options, such as hiding or showing grid area names, grid gaps, track sizes, and more.</span></span>  

<span data-ttu-id="4f0bc-200">永続的なグリッドのオーバーレイを切り替える2つの方法</span><span class="sxs-lookup"><span data-stu-id="4f0bc-200">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="4f0bc-201">**要素**ツールの DOM ツリーに表示されている grid 要素の隣にある**grid** lozenge を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-201">Choose the **Grid** lozenge next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="./media/grid-adorner.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/grid-adorner.msft.png":::
       <span data-ttu-id="4f0bc-203">要素ツールの Grid lozenge</span><span class="sxs-lookup"><span data-stu-id="4f0bc-203">Grid lozenge in Elements tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="4f0bc-204">[要素] ツールにある新しい **レイアウト** パネルを開き、強調表示する各グリッド要素の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-204">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="./media/grid-layout-zoom.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="4f0bc-206">レイアウトパネル</span><span class="sxs-lookup"><span data-stu-id="4f0bc-206">Layout panel</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="4f0bc-207">永続的なオーバーレイの構成</span><span class="sxs-lookup"><span data-stu-id="4f0bc-207">Configuring persistent overlays</span></span>  

<span data-ttu-id="4f0bc-208">新しい **レイアウト** パネルは、 **要素** ツールの Edge 86 以降の [ **スタイル** ] タブと [ **計算** ] タブに配置されていますが、持続的なオーバーレイの構成オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-208">The new **Layout** panel, located in the **Elements** tool alongside the **Styles** and **Computed** tabs in Edge 86 and later, surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-grid.msft.png":::
   <span data-ttu-id="4f0bc-210">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="4f0bc-210">CSS grid debugging feature</span></span>  
:::image-end:::  

### <span data-ttu-id="4f0bc-211">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-211">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="4f0bc-212">通常、 **要素** や **ネットワーク** などのツールは、devtools の上部にあるメインパネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-212">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="4f0bc-213">**3D ビュー**などのツール、および devtools の下部にある**引き出し**パネルで通常のみ開かれる**問題**。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-213">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="4f0bc-214">実験を選択した後、上下のパネル間でツールを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-214">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="4f0bc-215">ツールを移動するには、タブの上にマウスポインターを合わせて、コンテキストメニューの [ **先頭へ移動** ] または [ **下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-215">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="4f0bc-216">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-216">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="4f0bc-217">**ドロワー**パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-217">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-move-panels.msft.png":::
   <span data-ttu-id="4f0bc-219">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="4f0bc-219">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="4f0bc-220">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-220">Enable webhint</span></span>  

<span data-ttu-id="4f0bc-221">[webhint][WebhintMain] は、web サイトやローカル web ページにリアルタイムでフィードバックを提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-221">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="4f0bc-222">[Webhint][WebhintMain]によって提供されるフィードバックの種類。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-222">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="4f0bc-223">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="4f0bc-223">accessibility</span></span>  
*   <span data-ttu-id="4f0bc-224">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="4f0bc-224">cross-browser compatibility</span></span>  
*   <span data-ttu-id="4f0bc-225">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="4f0bc-225">security</span></span>  
*   <span data-ttu-id="4f0bc-226">処理</span><span class="sxs-lookup"><span data-stu-id="4f0bc-226">performance</span></span>  
*   <span data-ttu-id="4f0bc-227">PWA</span><span class="sxs-lookup"><span data-stu-id="4f0bc-227">PWAs</span></span>  
*   <span data-ttu-id="4f0bc-228">その他の一般的な web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="4f0bc-228">other common web development issues</span></span>  

<span data-ttu-id="4f0bc-229">[Webhint][WebhintMain]の実験では、[[問題][DevtoolsIssues]] パネルに webhint のフィードバックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-229">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="4f0bc-230">問題を選択すると、ソリューションのドキュメントと web サイト上の影響を受けるリソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-230">Select an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="4f0bc-231">リソースリンクを選んで、DevTools で関連する **ネットワーク**、 **ソース**、または **要素** のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-231">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-webhint.msft.png":::
   <span data-ttu-id="4f0bc-233">[ **問題** ] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="4f0bc-233">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="4f0bc-234">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="4f0bc-234">Enable Network Console</span></span>  

<span data-ttu-id="4f0bc-235">**ネットワーク本体** は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-235">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="4f0bc-236">**ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-236">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="4f0bc-237">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-237">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="4f0bc-238">**ネットワークコンソール**を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-238">To use the **Network Console**, use the following steps.</span></span>  

1.  <span data-ttu-id="4f0bc-239">[ **ネットワーク** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-239">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="4f0bc-240">変更して再送信するネットワーク要求を見つけます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-240">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="4f0bc-241">コンテキストメニューを開き (\ 右クリック \)、[ **編集と再生**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-241">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="4f0bc-242">**ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-242">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="4f0bc-243">[ **送信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-243">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/network-network-console.msft.png":::
   <span data-ttu-id="4f0bc-245">**Console**ドローワの**ネットワーク本体**</span><span class="sxs-lookup"><span data-stu-id="4f0bc-245">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="4f0bc-246">ソースオーダービューアー</span><span class="sxs-lookup"><span data-stu-id="4f0bc-246">Source Order Viewer</span></span>  

<span data-ttu-id="4f0bc-247">**ソースオーダービューアー** は、ページソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-247">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="4f0bc-248">オンスクリーン表示の順序は、ソースの順序とは異なる場合があります。これには、スクリーンリーダーとキーボードのユーザーが混乱させるます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-248">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="4f0bc-249">**ソース注文ビューアー**を使用して、画面上の表示順序とソースの順序の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-249">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="4f0bc-250">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-250">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="4f0bc-251">**ソースオーダービューアー**を使用するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-251">To use **Source Order Viewer**, use the following steps.</span></span>  

1.  <span data-ttu-id="4f0bc-252">[ **要素** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-252">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="4f0bc-253">[引き出し] \ (下) パネルで [ **アクセシビリティ** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-253">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="4f0bc-254">[ **ソース注文のビューアー** ] セクションで、[ **ソースの順序を表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-254">Under the **Source Order Viewer** section, select the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="4f0bc-255">任意の HTML 要素を強調表示して、ページソースの順序でオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-255">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="4f0bc-257">[**アクセシビリティ**] ウィンドウの**ソースオーダービューアー**</span><span class="sxs-lookup"><span data-stu-id="4f0bc-257">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## <span data-ttu-id="4f0bc-258">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="4f0bc-258">Previous experimental features</span></span>  

*   <span data-ttu-id="4f0bc-259">Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-259">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="4f0bc-260">Microsoft Edge バージョン86以降では、[ショートカット][DevtoolsCustomKeyboardShortcuts]キーをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-260">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  

## <span data-ttu-id="4f0bc-261">実験的な機能についてフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="4f0bc-261">Providing feedback on experimental features</span></span>  

<span data-ttu-id="4f0bc-262">Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f0bc-262">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="4f0bc-263">DevTools のフィードバックの **送信** アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="4f0bc-263">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="4f0bc-264">[@EdgeDevTools][TwitterEdgedevtools]ツイート</span><span class="sxs-lookup"><span data-stu-id="4f0bc-264">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="4f0bc-266">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="4f0bc-266">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageRotateIcon]: ./media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ./media/span-dark-icon.msft.png  
[ImageExperimentalApisIcon]: ./media/experimental-apis-dark-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D ビュー |Microsoft ドキュメント"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ./device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools でデバイスモードを使ってモバイルデバイスをシミュレートする |Microsoft Edge"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"

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
