---
description: Microsoft Edge の仮想デバイスを使用して、デュアルスクリーンと折りたたみ可能なデバイス向け Web サイトを強化します。
title: Microsoft Edge DevTools でデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, エミュレーション, デバイス, シミュレーション, モバイル, デュアルスクリーン, 折りたたみ可能, Surface Galaxy, Samsung Galaxy Fold
ms.openlocfilehash: bc91c0b7c917d82f169dc7d47e047a587d505353
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313282"
---
# <span data-ttu-id="01dcf-104">Microsoft Edge DevTools でデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="01dcf-104">Emulate dual-screen and foldable devices in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="01dcf-105">Microsoft Edge バージョン 89 以降では、次のデュアルスクリーン デバイスと折りたたみ可能なデバイスをエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="01dcf-105">In Microsoft Edge version 89 or later, you may emulate the following dual-screen and foldable devices.</span></span>  

*   [<span data-ttu-id="01dcf-106">Surface の一方</span><span class="sxs-lookup"><span data-stu-id="01dcf-106">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="01dcf-107">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="01dcf-107">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  
    
<span data-ttu-id="01dcf-108">デバイスをエミュレートし、次の状態を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="01dcf-108">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="01dcf-109">単一画面または折りたたまれた状態</span><span class="sxs-lookup"><span data-stu-id="01dcf-109">Single-screen or folded posture</span></span>  
*   <span data-ttu-id="01dcf-110">デュアルスクリーンまたは展開された体勢</span><span class="sxs-lookup"><span data-stu-id="01dcf-110">Dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="01dcf-111">試験的[な Web プラットフォーム API](#turn-on-experimental-apis)を有効にし[、CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用して、デュアルスクリーンと折りたたみ可能なデバイス向けの Web サイト \(または app\) を強化します。</span><span class="sxs-lookup"><span data-stu-id="01dcf-111">[Turn on experimental Web Platform APIs](#turn-on-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="Microsoft Edge で Surface のデュオをエミュレートする" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="01dcf-113">Microsoft Edge で Surface のデュオをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="01dcf-113">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

## <span data-ttu-id="01dcf-114">試験的な API を有効にする</span><span class="sxs-lookup"><span data-stu-id="01dcf-114">Turn on experimental APIs</span></span>  

<span data-ttu-id="01dcf-115">[CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用するには、Microsoft Edge でフラグ `Experimental Web Platform features` をオンにします。</span><span class="sxs-lookup"><span data-stu-id="01dcf-115">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="01dcf-116">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="01dcf-116">Complete the following steps.</span></span>  

1.  <span data-ttu-id="01dcf-117">に移動します `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="01dcf-117">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="01dcf-118">[検索フラグ **] ボックスに**、「試験的な Web プラットフォーム機能」フラグを入力し、[無効] を [有効] `Experimental Web Platform features` に**変更します**。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="01dcf-118">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="01dcf-119">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="01dcf-119">Restart Microsoft Edge.</span></span>  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="[試験的な Web プラットフォーム機能] フラグをオンにする" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="01dcf-121">[試験的な **Web プラットフォーム機能] フラグをオン** にする</span><span class="sxs-lookup"><span data-stu-id="01dcf-121">Turn on the **Experimental Web Platform features** flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="01dcf-122">[CSS][DualScreenDocsCssMedia]メディア クエリまたは[JavaScript Windows セグメント][DualScreenDocsJSAPI]列挙 API を使用して Surface Surface の Web サイトまたはアプリを強化する場合は[、Surface Surface][SurfaceDevicesDuo][デバイス][SurfaceDevicesDuo]の Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリで試験的な**Web**プラットフォーム機能フラグもオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01dcf-122">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also turn on the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="01dcf-123">デスクトップの[Microsoft][MicrosoftEdge] [Edge][SurfaceDevicesDuo]で試験的**な Web**プラットフォーム機能のフラグがオンになっていて[、Android Microsoft Edge][GooglePlayMicrosoftEdge]アプリでオフになっている場合、デスクトップの Surface Emulator の Web サイトまたはアプリの動作が、Microsoft Edge デスクトップの Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリと一致しません。</span><span class="sxs-lookup"><span data-stu-id="01dcf-123">If the **Experimental Web Platform features** flag is turned on in [desktop Microsoft Edge][MicrosoftEdge] and turned off in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="01dcf-124">フラグが Android とデスクトップの Microsoft Edge で一致し、デスクトップの Microsoft Edge で Surface Emulator エミュレーターが正常に使用 [されたことを確認します][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="01dcf-124">Ensure that the flags match across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

## <span data-ttu-id="01dcf-125">折りたたみ可能なデバイスとデュアルスクリーン デバイスでのテスト</span><span class="sxs-lookup"><span data-stu-id="01dcf-125">Test on foldable and dual-screen devices</span></span>  

<span data-ttu-id="01dcf-126">Microsoft Edge でデュアルスクリーンの位置で [Surface Over][SurfaceDevicesDuo] をエミュレートすると、Web サイトまたはアプリの上に、"2 つの画面の間のスペース\" が描画されます。</span><span class="sxs-lookup"><span data-stu-id="01dcf-126">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="01dcf-127">エミュレートされたディスプレイは[、Surface Surface の合][SurfaceDevicesDuo]図での実行中に Microsoft Edge [Android][GooglePlayMicrosoftEdge]アプリで Web サイト \(または app\) がレンダリングされる方法と一致します。</span><span class="sxs-lookup"><span data-stu-id="01dcf-127">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] while running on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="01dcf-128">Web サイト \(または app\) を更新して、より良い画面を表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="01dcf-128">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="01dcf-129">For more information about adapting your website \(or app\) to the work [with the windows.][DualScreenIntroductionHowWorkSeam]</span><span class="sxs-lookup"><span data-stu-id="01dcf-129">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam].</span></span>  

<span data-ttu-id="01dcf-130">デバイス [ツール バーには、][DevtoolsDeviceModeIndexSimulateMobileViewport] 複数の位置と向きで Web サイトまたはアプリをテストするのに役立つ追加機能があります。</span><span class="sxs-lookup"><span data-stu-id="01dcf-130">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="01dcf-131">ビューポート **を横向** きに回転するには、回転 ![ ](../media/rotate-dark-icon.msft.png) \( Rotate \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="01dcf-131">Choose **Rotate** \(![Rotate](../media/rotate-dark-icon.msft.png)\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="01dcf-132">機能を Span \( **Span** \) と組み合わせて、単一画面または折りたたまれた状態とデュアルスクリーンの状態、または展開された状態を切り ![ ](../media/span-dark-icon.msft.png) 替える。</span><span class="sxs-lookup"><span data-stu-id="01dcf-132">Combine the feature with **Span** \(![Span](../media/span-dark-icon.msft.png)\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="01dcf-133">これらの機能を組み合わせて、4 つの考えられるすべての位置と向きで Web サイトまたはアプリをテストできます。</span><span class="sxs-lookup"><span data-stu-id="01dcf-133">Together, the features allow you to test your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="01dcf-135">デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス</span><span class="sxs-lookup"><span data-stu-id="01dcf-135">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="01dcf-136">Experimental **Web Platform features** \( ExperimentalApis \) アイコンには、Experimental Web Platform 機能フラグの ![ ](../media/experimental-apis-dark-icon.msft.png) **状態が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="01dcf-136">The **Experimental Web Platform features** \(![ExperimentalApis](../media/experimental-apis-dark-icon.msft.png)\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="01dcf-137">フラグがオンの場合、アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="01dcf-137">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="01dcf-138">フラグがオフの場合、アイコンは強調表示されません。</span><span class="sxs-lookup"><span data-stu-id="01dcf-138">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="01dcf-139">フラグを \(or off\) に切り替えるには、アイコンを選択するか、フラグに移動して `edge://flags` 切り替えます。</span><span class="sxs-lookup"><span data-stu-id="01dcf-139">To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.</span></span>  

> [!NOTE]
> <span data-ttu-id="01dcf-140">現在の既知の問題の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="01dcf-140">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="01dcf-141">[Microsoft][RemoteDesktopClientDocs]リモート デスクトップ クライアントを使ってリモート PC に接続し[、Surface Galaxy][SurfaceDevicesDuo]や Samsung [Galaxy Fold][SamsungMobileGalaxyFold]をエミュレートすると、ポインターが動き、つまずく可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01dcf-141">When you use a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="01dcf-142">If you run into the issue, [send feedback](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span><span class="sxs-lookup"><span data-stu-id="01dcf-142">If you run into the issue, [send feedback](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <span data-ttu-id="01dcf-143">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="01dcf-143">Additional Resources</span></span>  

<span data-ttu-id="01dcf-144">ここでは、デュアルスクリーン デバイス用に Web サイト \(または app\) を強化するのに役立つ可能性があるその他のリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="01dcf-144">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices.</span></span>  

*   <span data-ttu-id="01dcf-145">デュアルスクリーン デバイスでの Web 開発の詳細については、「デュアルスクリーン Web [エクスペリエンス」に移動してください][DualScreenWebIndex]。</span><span class="sxs-lookup"><span data-stu-id="01dcf-145">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="01dcf-146">Surface [Emulator エミュレーターをインストールします][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="01dcf-146">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="01dcf-147">Surface Emulator エミュレーターは、Microsoft Edge のエミュレーターとは異なります。Android を実行し [、Android Studio と統合します][AndroidDeveloperStudio]。</span><span class="sxs-lookup"><span data-stu-id="01dcf-147">The Surface Duo emulator is different from the emulator in Microsoft Edge, runs Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="01dcf-148">詳しくは [、Surface Sdk の取得に関するページをご覧ください][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="01dcf-148">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

## <span data-ttu-id="01dcf-149">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="01dcf-149">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Edge"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Emulator エミュレーター を取得|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Emulator エミュレーター を使|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアントの|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Surface の |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  
