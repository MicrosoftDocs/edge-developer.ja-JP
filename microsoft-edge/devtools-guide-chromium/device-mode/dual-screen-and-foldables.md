---
description: Microsoft Edge の仮想デバイスを使用して、デュアルスクリーンおよび折りたたみ可能なデバイス用の Web サイトを強化します。
title: Microsoft Edge DevTools でデュアルスクリーンデバイスと折りたたみデバイスをエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, エミュレーション, デバイス, シミュレーション, モバイル, デュアルスクリーン, 折りたたみ式, Surface Duo, Samsung Galaxy Fold
ms.openlocfilehash: bc91c0b7c917d82f169dc7d47e047a587d505353
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313282"
---
# <span data-ttu-id="0ae75-104">Microsoft Edge DevTools でデュアルスクリーンデバイスと折りたたみデバイスをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="0ae75-104">Emulate dual-screen and foldable devices in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="0ae75-105">Microsoft Edge バージョン 89 以降では、次のデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="0ae75-105">In Microsoft Edge version 89 or later, you may emulate the following dual-screen and foldable devices.</span></span>  

*   [<span data-ttu-id="0ae75-106">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="0ae75-106">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="0ae75-107">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="0ae75-107">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  
    
<span data-ttu-id="0ae75-108">デバイスをエミュレートし、次のポスチャを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0ae75-108">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="0ae75-109">1 画面または折りたたまれた姿勢</span><span class="sxs-lookup"><span data-stu-id="0ae75-109">Single-screen or folded posture</span></span>  
*   <span data-ttu-id="0ae75-110">デュアルスクリーンまたは展開された姿勢</span><span class="sxs-lookup"><span data-stu-id="0ae75-110">Dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="0ae75-111">実験的な[Web プラットフォーム API](#turn-on-experimental-apis)を有効にし[、CSS][DualScreenDocsCssMedia]メディア画面にまたがる機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用して、デュアルスクリーンおよび折りたたみ可能なデバイス用の Web サイト \(または app\) を強化します。</span><span class="sxs-lookup"><span data-stu-id="0ae75-111">[Turn on experimental Web Platform APIs](#turn-on-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="Microsoft Edge で Surface Duo をエミュレートする" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="0ae75-113">Microsoft Edge で Surface Duo をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="0ae75-113">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

## <span data-ttu-id="0ae75-114">実験的な API を有効にする</span><span class="sxs-lookup"><span data-stu-id="0ae75-114">Turn on experimental APIs</span></span>  

<span data-ttu-id="0ae75-115">CSS メディア画面 [スパン機能][DualScreenDocsCssMedia] と [JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用するには、Microsoft Edge で `Experimental Web Platform features` フラグをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0ae75-115">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="0ae75-116">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0ae75-116">Complete the following steps.</span></span>  

1.  <span data-ttu-id="0ae75-117">`edge://flags` に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ae75-117">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="0ae75-118">[検索フラグ **] テキスト**ボックスに「実験 Web プラットフォーム機能フラグ」と入力し、[無効] を [有効] `Experimental Web Platform features` **に\*\*\*\*変更します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0ae75-118">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="0ae75-119">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-119">Restart Microsoft Edge.</span></span>  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="[実験用 Web プラットフォームの機能] フラグをオンにする" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="0ae75-121">[実験用 **Web プラットフォームの機能] フラグをオン** にする</span><span class="sxs-lookup"><span data-stu-id="0ae75-121">Turn on the **Experimental Web Platform features** flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="0ae75-122">[CSS][DualScreenDocsCssMedia]メディア クエリまたは[JavaScript Windows セグメント][DualScreenDocsJSAPI]列挙 API を使用して Surface [Duo][SurfaceDevicesDuo]の Web サイトまたはアプリを\*\*\*\* 強化する場合は、Surface [Duo][SurfaceDevicesDuo]デバイスの Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリの [実験用 Web プラットフォーム機能] フラグもオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ae75-122">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also turn on the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="0ae75-123">[][SurfaceDevicesDuo]デスクトップ Microsoft [Edge][MicrosoftEdge]で [実験用**Web**プラットフォームの機能] フラグがオンになっていて[、Android][GooglePlayMicrosoftEdge]Microsoft Edge アプリでオフになっている場合、デスクトップ Microsoft Edge の Surface Duo エミュレーターでの Web サイトまたはアプリの動作が Surface Duo の Android Microsoft [Edge][GooglePlayMicrosoftEdge]アプリと一致しません。</span><span class="sxs-lookup"><span data-stu-id="0ae75-123">If the **Experimental Web Platform features** flag is turned on in [desktop Microsoft Edge][MicrosoftEdge] and turned off in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="0ae75-124">フラグが Android とデスクトップの Microsoft Edge で一致し、デスクトップ Microsoft Edge で Surface Duo エミュレーターが正常に使用 [されたことを確認します][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-124">Ensure that the flags match across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

## <span data-ttu-id="0ae75-125">折りたたみおよびデュアルスクリーン デバイスでのテスト</span><span class="sxs-lookup"><span data-stu-id="0ae75-125">Test on foldable and dual-screen devices</span></span>  

<span data-ttu-id="0ae75-126">Microsoft Edge のデュアルスクリーンの姿勢で [Surface Duo][SurfaceDevicesDuo] をエミュレートすると、シーム \(2 つの画面の間のスペース\) が Web サイトまたはアプリの上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="0ae75-126">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="0ae75-127">エミュレートされた表示は [、Surface][GooglePlayMicrosoftEdge] Duo での実行中に Web サイト \(または app\) が Microsoft Edge Android アプリでレンダリングする方法と [一致します][SurfaceDevicesDuo]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-127">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] while running on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="0ae75-128">縫い目に沿って表示するには、Web サイト \(または app\) を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ae75-128">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="0ae75-129">Web サイト \(または app\) を継ぎ目に合わせる方法の詳細については、「縫い目を操作する方法」 [を参照してください][DualScreenIntroductionHowWorkSeam]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-129">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam].</span></span>  

<span data-ttu-id="0ae75-130">デバイス [ツールバーには、][DevtoolsDeviceModeIndexSimulateMobileViewport] 複数の姿勢と向きで Web サイトやアプリをテストするのに役立つ追加機能があります。</span><span class="sxs-lookup"><span data-stu-id="0ae75-130">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="0ae75-131">ビューポート **を横向** き ![ に回転 ](../media/rotate-dark-icon.msft.png) するには、[回転]\(回転\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ae75-131">Choose **Rotate** \(![Rotate](../media/rotate-dark-icon.msft.png)\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="0ae75-132">機能を Span \( **Span** \) と組み合わせて、単一画面または折りたたまれた姿勢とデュアルスクリーンまたは展開された姿勢を ![ ](../media/span-dark-icon.msft.png) 切り替えてください。</span><span class="sxs-lookup"><span data-stu-id="0ae75-132">Combine the feature with **Span** \(![Span](../media/span-dark-icon.msft.png)\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="0ae75-133">この機能を組み合わせて、4 つの可能なすべての姿勢と向きで Web サイトまたはアプリをテストできます。</span><span class="sxs-lookup"><span data-stu-id="0ae75-133">Together, the features allow you to test your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンおよび折りたたみ可能なデバイスの姿勢と向きのマトリックス" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="0ae75-135">デュアルスクリーンおよび折りたたみ可能なデバイスの姿勢と向きのマトリックス</span><span class="sxs-lookup"><span data-stu-id="0ae75-135">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="0ae75-136">実験 **Web プラットフォーム機能** \( ExperimentalApis \) アイコンは、実験 Web プラットフォーム機能フラグの状態 ![ ](../media/experimental-apis-dark-icon.msft.png) **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="0ae75-136">The **Experimental Web Platform features** \(![ExperimentalApis](../media/experimental-apis-dark-icon.msft.png)\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="0ae75-137">フラグをオンにすると、アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ae75-137">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="0ae75-138">フラグがオフの場合、アイコンは強調表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ae75-138">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="0ae75-139">\(or off\) フラグを有効にするには、アイコンを選択するか、フラグに移動して `edge://flags` 切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0ae75-139">To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.</span></span>  

> [!NOTE]
> <span data-ttu-id="0ae75-140">現在の既知の問題の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0ae75-140">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="0ae75-141">[Microsoft][RemoteDesktopClientDocs]リモート デスクトップ クライアントを使用してリモート PC に接続し[、Surface Duo][SurfaceDevicesDuo]または Samsung [Galaxy Fold][SamsungMobileGalaxyFold]をエミュレートすると、ポインターが揺れや吃音を発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ae75-141">When you use a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="0ae75-142">問題が発生した場合は、フィードバック [を送信します](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="0ae75-142">If you run into the issue, [send feedback](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <span data-ttu-id="0ae75-143">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="0ae75-143">Additional Resources</span></span>  

<span data-ttu-id="0ae75-144">デュアルスクリーン デバイスの Web サイト \(または app\) の強化に役立つその他のリソースを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0ae75-144">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices.</span></span>  

*   <span data-ttu-id="0ae75-145">デュアルスクリーン デバイスでの Web 開発の詳細については、「デュアルスクリーン Web エクスペリエンス [」に移動します][DualScreenWebIndex]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-145">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="0ae75-146">Surface [Duo エミュレーターをインストールします][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-146">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="0ae75-147">Surface Duo エミュレーターは、Microsoft Edge のエミュレーターとは異なります。Android を実行し [、Android Studio と統合します][AndroidDeveloperStudio]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-147">The Surface Duo emulator is different from the emulator in Microsoft Edge, runs Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="0ae75-148">詳細については [、「Get the Surface Duo SDK」に移動します][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="0ae75-148">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

## <span data-ttu-id="0ae75-149">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="0ae75-149">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードでモバイル デバイスをシミュレート|Microsoft Edge"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo エミュレーターの|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアントの|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  
