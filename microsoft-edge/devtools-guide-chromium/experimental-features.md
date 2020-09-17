---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: ce8388e8065055e6002bd8541101bef658c7a403
ms.sourcegitcommit: 744e2ecf42bcc427ae33e5dadbf6cd48ee0ab6a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016748"
---
# <span data-ttu-id="cdfea-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="cdfea-104">Experimental features</span></span>  

<span data-ttu-id="cdfea-105">Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="cdfea-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="cdfea-106">各機能がリリースされる前に、テストして、[フィードバックを提供](#providing-feedback-on-experimental-features) することができます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-106">You may test and p[provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="cdfea-107">Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="cdfea-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-108">Turn on experimental features</span></span>  

<span data-ttu-id="cdfea-109">Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-109">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="cdfea-110">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-110">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="cdfea-111">[ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-111">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="cdfea-112">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-112">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="cdfea-113">[ [設定][DevToolsCustomizeSettings] ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="cdfea-114">を選択し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="cdfea-115">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="cdfea-116">[ **設定** ] ウィンドウの左側で、[ **実験** ] セクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.msft.png":::
       <span data-ttu-id="cdfea-118">DevTools の設定での実験の一覧</span><span class="sxs-lookup"><span data-stu-id="cdfea-118">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cdfea-119">[ **実験** ] ページで、利用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cdfea-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="cdfea-120">Microsoft Edge DevTools を閉じてからもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-120">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="cdfea-121">実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cdfea-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="cdfea-122">実験的な機能を無効にするには、[ **実験** ] ページを開き、無効にする実験的機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="cdfea-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="cdfea-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="cdfea-123">Highlighted experimental features</span></span>  

<span data-ttu-id="cdfea-124">以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="cdfea-125">実験的機能</span><span class="sxs-lookup"><span data-stu-id="cdfea-125">Experimental feature</span></span> | <span data-ttu-id="cdfea-126">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="cdfea-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="cdfea-127">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="cdfea-127">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="cdfea-128">84以降</span><span class="sxs-lookup"><span data-stu-id="cdfea-128">84 or later</span></span> |  
| [<span data-ttu-id="cdfea-129">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-129">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="cdfea-130">85以降</span><span class="sxs-lookup"><span data-stu-id="cdfea-130">85 or later</span></span> |  
| [<span data-ttu-id="cdfea-131">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-131">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="cdfea-132">85以降</span><span class="sxs-lookup"><span data-stu-id="cdfea-132">85 or later</span></span> |  
| [<span data-ttu-id="cdfea-133">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-133">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="cdfea-134">85以降</span><span class="sxs-lookup"><span data-stu-id="cdfea-134">85 or later</span></span> |  
| [<span data-ttu-id="cdfea-135">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-135">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="cdfea-136">85以降</span><span class="sxs-lookup"><span data-stu-id="cdfea-136">85 or later</span></span> |  
| [<span data-ttu-id="cdfea-137">ソースオーダービューアーを有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-137">Enable Source Order Viewer</span></span>](#enable-source-order-viewer) | <span data-ttu-id="cdfea-138">86以降</span><span class="sxs-lookup"><span data-stu-id="cdfea-138">86 or later</span></span> |  

### <span data-ttu-id="cdfea-139">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="cdfea-139">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="cdfea-140">Microsoft Edge で2つの新しいデュアル画面と折りたたみ式デバイスをエミュレートするための追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-140">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="cdfea-141">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="cdfea-141">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="cdfea-142">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="cdfea-142">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  

<span data-ttu-id="cdfea-143">デバイスをエミュレートし、次の後処理を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-143">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="cdfea-144">シングルスクリーンまたは折り目</span><span class="sxs-lookup"><span data-stu-id="cdfea-144">single-screen or folded posture</span></span>  
*   <span data-ttu-id="cdfea-145">デュアルスクリーンまたは折る</span><span class="sxs-lookup"><span data-stu-id="cdfea-145">dual-screen or unfolded posture</span></span>  
 
<span data-ttu-id="cdfea-146">[実験的な Web Platform api を有効](#enable-experimental-apis) にして、 [CSS メディアの画面スパン機能][DualScreenDocsCssMedia] と [JavaScript getwindowsegments API][DualScreenDocsJSAPI] を使用して、デュアルスクリーンデバイスと折りたたみ式デバイス用の web サイト (またはアプリ) を強化します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-146">[Enable experimental Web Platform APIs](#enable-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>

:::image type="complex" source="./media/experiments-surface-duo-emulation.msft.png" alt-text="Microsoft Edge で Surface Duo をエミュレートする" lightbox="./media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="cdfea-148">Microsoft Edge で Surface Duo をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="cdfea-148">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="cdfea-149">実験的な Api を有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-149">Enable experimental APIs</span></span>  

<span data-ttu-id="cdfea-150">[CSS メディアの画面スパン機能][DualScreenDocsCssMedia]と[JavaScript GETWINDOWSEGMENTS API][DualScreenDocsJSAPI]を使用するには、 `Experimental Web Platform features` Microsoft Edge でフラグをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cdfea-150">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="cdfea-151">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-151">Complete the following steps.</span></span>

1.  <span data-ttu-id="cdfea-152">に移動 `edge://flags` します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-152">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="cdfea-153">[ **検索フラグ** ] ボックスに、「 `Experimental Web Platform features` 実験的な **Web Platform 機能** 」というフラグを選択して、[ **無効** ] を [ **有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-153">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="cdfea-154">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="cdfea-154">Restart Microsoft Edge.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="実験的な Web Platform 機能のフラグを有効にする" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="cdfea-156">実験的な Web Platform 機能のフラグを有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-156">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="cdfea-157">[CSS メディアクエリ][DualScreenDocsCssMedia]または[JavaScript WINDOWS セグメント列挙 API][DualScreenDocsJSAPI]を使用して[surface duo][SurfaceDevicesDuo]の web サイトまたはアプリを強化する場合は、 [Surface duo][SurfaceDevicesDuo]デバイス上の[Android Microsoft Edge アプリ][GooglePlayMicrosoftEdge]の試用版の**Web プラットフォーム機能**フラグも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdfea-157">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>
> 
> <span data-ttu-id="cdfea-158">[Microsoft edge][MicrosoftEdge] [アプリの android][GooglePlayMicrosoftEdge]microsoft Edge で**実験的な Web Platform 機能**のフラグが有効になっている場合、デスクトップ microsoft edge の surface duo エミュレーターの web サイトまたはアプリの動作は[surface duo][SurfaceDevicesDuo]の[Android microsoft edge アプリ][GooglePlayMicrosoftEdge]と一致しません。</span><span class="sxs-lookup"><span data-stu-id="cdfea-158">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge will not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="cdfea-159">[デスクトップ Microsoft edge][MicrosoftEdge]で Surface Duo エミュレーターを正常に使用するために、Android とデスクトップの microsoft edge の間でフラグが一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-159">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="cdfea-160">折りたたみ式とデュアルスクリーンデバイスでのテスト</span><span class="sxs-lookup"><span data-stu-id="cdfea-160">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="cdfea-161">Microsoft Edge のデュアル画面の姿勢で [Surface Duo][SurfaceDevicesDuo] をエミュレートすると、ユーザーの web サイトまたはアプリ上で、継ぎ目 (2 つの画面間のスペース) が描画されます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-161">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="cdfea-162">エミュレートされたディスプレイは、web サイト \ (またはアプリ \) と[Surface Duo][SurfaceDevicesDuo]の[Microsoft Edge Android アプリ][GooglePlayMicrosoftEdge]での表示方法に一致します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-162">The emulated display matches the way your website \(or app\) will render in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="cdfea-163">お客様の web サイト \ (またはアプリ \) を更新して、継ぎ目に合わせて表示を改善しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdfea-163">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="cdfea-164">Web サイトの外観を seam に適合させる方法の詳細については、Surface Duo のドキュメントで [seam を操作する方法][DualScreenIntroductionHowWorkSeam] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-164">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam] in the Surface Duo documentation.</span></span>  

<span data-ttu-id="cdfea-165">[デバイスツールバー][DevtoolsDeviceModeIndexSimulateMobileViewport]には、web サイトまたはアプリを複数の方法でテストするための追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cdfea-165">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="cdfea-166">**Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 \ (回転 \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-166">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="cdfea-167">この機能を **スパン** \ ( ![ スパン \) と組み合わせると、シングル画面で、または折る、または折り目を切り替えることが ][ImageSpanIcon] できます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-167">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="cdfea-168">これらの機能により、web サイトやアプリを4つのすべての方法でテストできます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-168">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="cdfea-170">デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス</span><span class="sxs-lookup"><span data-stu-id="cdfea-170">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="cdfea-171">**実験的な Web platform 機能**\ ( ![ ExperimentalApis ][ImageExperimentalApisIcon] \) アイコンは、**実験的な web プラットフォーム機能**のフラグの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-171">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="cdfea-172">フラグがオンになっている場合は、アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-172">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="cdfea-173">フラグがオフになっている場合、アイコンは強調表示されません。</span><span class="sxs-lookup"><span data-stu-id="cdfea-173">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="cdfea-174">フラグをオン (またはオフ) にするには、フラグに移動 `edge://flags` して切り替えます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-174">To turn on \(or off\) the flag, navigate to `edge://flags` and toggle the flag.</span></span>  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->

<span data-ttu-id="cdfea-175">ここでは、デュアルスクリーンデバイス向けの web サイト (またはアプリ) を強化するために役立つその他のリソースを紹介します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-175">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices:</span></span>
*   <span data-ttu-id="cdfea-176">デュアルスクリーンデバイスでの web 開発の詳細については、「 [デュアルスクリーン web エクスペリエンス][DualScreenWebIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-176">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="cdfea-177">[Surface Duo エミュレーター][DualScreenAndroidUseEmulator]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdfea-177">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="cdfea-178">これは、Microsoft Edge のエミュレーターとは異なり、Android を実行している Surface Duo のエミュレートと [Android Studio][AndroidDeveloperStudio]との統合です。</span><span class="sxs-lookup"><span data-stu-id="cdfea-178">It is different from the emulator in Microsoft Edge, emulates the Surface Duo running Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="cdfea-179">詳細については、「 [Surface DUO SDK の入手][DualScreenAndroidGetDuoSdk]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-179">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

> [!NOTE]
> <span data-ttu-id="cdfea-180">次に、現在の既知の問題の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-180">The following is a list of current known issues:</span></span>
> *   <span data-ttu-id="cdfea-181">[Microsoft リモートデスクトップクライアント][RemoteDesktopClientDocs]を使ってリモート PC に接続し、 [Surface Duo][SurfaceDevicesDuo]または[Samsung Galaxy の折りたたみ][SamsungMobileGalaxyFold]をエミュレートすると、ポインターがシェイクまたは途切れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cdfea-181">When using a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="cdfea-182">この問題が発生した場合は、 [フィードバックを送信](#providing-feedback-on-experimental-features)してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-182">If you run into this issue, [send feedback](#providing-feedback-on-experimental-features).</span></span>  

### <span data-ttu-id="cdfea-183">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-183">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="cdfea-184">CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-184">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="cdfea-185">DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-185">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.msft.png":::
   <span data-ttu-id="cdfea-187">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="cdfea-187">CSS grid debugging feature</span></span>  
:::image-end:::  

<span data-ttu-id="cdfea-188">最新の実験的な機能をプレビューするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-188">To preview the latest experimental features, complete the following actions.</span></span>  

1.  <span data-ttu-id="cdfea-189">[ **実験** ] セクションで、[ **新しい CSS グリッドのデバッグ機能を有効にする] チェックボックスをオンにします (再起動後に、レイアウトサイドバーウィンドウで使用可能な構成オプション)** 。</span><span class="sxs-lookup"><span data-stu-id="cdfea-189">In the **Experiments** section, choose the **Enable new CSS Grid debugging features (configuration options available in Layout sidebar pane in Elements after restart)** checkbox.</span></span>  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="cdfea-190">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-190">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="cdfea-191">通常、 **要素** や **ネットワーク** などのツールは、devtools の上部にあるメインパネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-191">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="cdfea-192">**3D ビュー**などのツール、および devtools の下部にある**引き出し**パネルで通常のみ開かれる**問題**。</span><span class="sxs-lookup"><span data-stu-id="cdfea-192">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="cdfea-193">実験を選択した後、上下のパネル間でツールを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-193">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="cdfea-194">ツールを移動するには、タブの上にマウスポインターを合わせて、コンテキストメニューの [ **先頭へ移動** ] または [ **下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-194">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="cdfea-195">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-195">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="cdfea-196">**ドロワー**パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-196">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.msft.png":::
   <span data-ttu-id="cdfea-198">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="cdfea-198">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="cdfea-199">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-199">Enable webhint</span></span>  

<span data-ttu-id="cdfea-200">[webhint][WebhintMain] は、web サイトやローカル web ページにリアルタイムでフィードバックを提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="cdfea-200">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="cdfea-201">[Webhint][WebhintMain]によって提供されるフィードバックの種類。</span><span class="sxs-lookup"><span data-stu-id="cdfea-201">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="cdfea-202">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="cdfea-202">accessibility</span></span>  
*   <span data-ttu-id="cdfea-203">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="cdfea-203">cross-browser compatibility</span></span>  
*   <span data-ttu-id="cdfea-204">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="cdfea-204">security</span></span>  
*   <span data-ttu-id="cdfea-205">処理</span><span class="sxs-lookup"><span data-stu-id="cdfea-205">performance</span></span>  
*   <span data-ttu-id="cdfea-206">PWA</span><span class="sxs-lookup"><span data-stu-id="cdfea-206">PWAs</span></span>  
*   <span data-ttu-id="cdfea-207">その他の一般的な web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="cdfea-207">other common web development issues</span></span>  

<span data-ttu-id="cdfea-208">[Webhint][WebhintMain]の実験では、[[問題][DevtoolsIssues]] パネルに webhint のフィードバックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-208">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="cdfea-209">問題を選択すると、ソリューションのドキュメントと web サイト上の影響を受けるリソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-209">Select an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="cdfea-210">リソースリンクを選んで、DevTools で関連する **ネットワーク**、 **ソース**、または **要素** のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-210">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.msft.png":::
   <span data-ttu-id="cdfea-212">[ **問題** ] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="cdfea-212">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="cdfea-213">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-213">Enable Network Console</span></span>  

<span data-ttu-id="cdfea-214">**ネットワーク本体** は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="cdfea-214">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="cdfea-215">**ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-215">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="cdfea-216">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-216">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="cdfea-217">**ネットワークコンソール**を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-217">To use the **Network Console**, use the following steps.</span></span>    

1.  <span data-ttu-id="cdfea-218">[ **ネットワーク** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-218">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="cdfea-219">変更して再送信するネットワーク要求を見つけます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-219">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="cdfea-220">コンテキストメニューを開き (\ 右クリック \)、[ **編集と再生**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-220">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="cdfea-221">**ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-221">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="cdfea-222">[ **送信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-222">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="Console ドローワのネットワーク本体" lightbox="./media/network-network-console.msft.png":::
   <span data-ttu-id="cdfea-224">**Console**ドローワの**ネットワーク本体**</span><span class="sxs-lookup"><span data-stu-id="cdfea-224">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="cdfea-225">ソースオーダービューアーを有効にする</span><span class="sxs-lookup"><span data-stu-id="cdfea-225">Enable Source Order Viewer</span></span>  

<span data-ttu-id="cdfea-226">**ソースオーダービューアー** は、ページソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="cdfea-226">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="cdfea-227">オンスクリーン表示の順序は、ソースの順序とは異なる場合があります。これには、スクリーンリーダーとキーボードのユーザーが混乱させるます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-227">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="cdfea-228">**ソース注文ビューアー**を使用して、画面上の表示順序とソースの順序の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-228">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="cdfea-229">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="cdfea-229">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="cdfea-230">ソースオーダービューアーを使用するには:</span><span class="sxs-lookup"><span data-stu-id="cdfea-230">To use Source Order Viewer:</span></span>  

1.  <span data-ttu-id="cdfea-231">[ **要素** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="cdfea-231">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="cdfea-232">[引き出し] \ (下) パネルで [ **アクセシビリティ** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="cdfea-232">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="cdfea-233">[ **ソース注文のビューアー** ] セクションで、[ **ソースの順序を表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cdfea-233">Under the **Source Order Viewer** section, select the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="cdfea-234">任意の HTML 要素を強調表示して、ページソースの順序でオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-234">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソースオーダービューアー" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="cdfea-236">[**アクセシビリティ**] ウィンドウの**ソースオーダービューアー**</span><span class="sxs-lookup"><span data-stu-id="cdfea-236">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## <span data-ttu-id="cdfea-237">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="cdfea-237">Previous experimental features</span></span>  

*   <span data-ttu-id="cdfea-238">Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="cdfea-238">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="cdfea-239">Microsoft Edge バージョン86以降では、[ショートカット][DevtoolsCustomKeyboardShortcuts]キーをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cdfea-239">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  

## <span data-ttu-id="cdfea-240">実験的な機能についてフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="cdfea-240">Providing feedback on experimental features</span></span>  

<span data-ttu-id="cdfea-241">Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="cdfea-241">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="cdfea-242">DevTools のフィードバックの **送信** アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="cdfea-242">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="cdfea-243">[@EdgeDevTools][TwitterEdgedevtools]ツイート</span><span class="sxs-lookup"><span data-stu-id="cdfea-243">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="cdfea-245">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="cdfea-245">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
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
