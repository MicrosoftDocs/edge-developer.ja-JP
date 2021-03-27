---
description: リモート デバッグ Surface Duo エミュレーターの使用を開始します。
title: リモート デバッグ Surface Duo エミュレーターの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/25/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, リモート デバッグ, android, surface duo
ms.openlocfilehash: 49b16f3c920735b34d44455bae437442cac3bf6e
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461242"
---
# <a name="get-started-with-remote-debugging-surface-duo-emulators"></a><span data-ttu-id="86c18-104">Surface Duo エミュレーターのリモート デバッグの開始</span><span class="sxs-lookup"><span data-stu-id="86c18-104">Get started with remote debugging Surface Duo emulators</span></span>  

<span data-ttu-id="86c18-105">この記事では [、Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx] のデスクトップ インスタンスから Surface Duo エミュレーター上の Microsoft [Edge][MicrosoftSurfaceDevicesSurfaceDuo] アプリで Web コンテンツをリモートでデバッグするプロセスについて [説明します][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="86c18-105">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on a [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo] emulator from a desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="86c18-106">Surface Duo デバイスでのデバッグの詳細については、Android デバイスのリモート デバッグに関するガイド [に従ってください][DevtoolsRemoteDebuggingMain]。</span><span class="sxs-lookup"><span data-stu-id="86c18-106">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][DevtoolsRemoteDebuggingMain].</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="86c18-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="86c18-107">Before you begin</span></span>

<span data-ttu-id="86c18-108">Surface Duo [エミュレーターを実行する前][MicrosoftDownload100847] に Surface Duo SDK [をインストールします][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="86c18-108">Install the [Surface Duo SDK][MicrosoftDownload100847] before running the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="86c18-109">詳細については [、「Get the Surface Duo SDK」に移動します][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="86c18-109">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

## <a name="step-1-navigate-to-edgeinspect"></a><span data-ttu-id="86c18-110">手順 1: [手順 1] に移動 edge://inspect</span><span class="sxs-lookup"><span data-stu-id="86c18-110">Step 1: Navigate to edge://inspect</span></span>  

<span data-ttu-id="86c18-111">Microsoft Edge のデスクトップ インスタンスを [開き][MicrosoftEdge]、に移動します `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="86c18-111">Open a desktop instance of [Microsoft Edge][MicrosoftEdge], and navigate to `edge://inspect`.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="デスクトップ edge://inspect Microsoft Edge の [新しいページ] ページ" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   <span data-ttu-id="86c18-113">デスクトップ `edge://inspect` 上の Microsoft Edge のページ</span><span class="sxs-lookup"><span data-stu-id="86c18-113">The `edge://inspect` page in Microsoft Edge on the desktop</span></span>  
:::image-end:::

> [!NOTE]
> <span data-ttu-id="86c18-114">ページで `edge://inspect` Surface Duo エミュレーターが認識されない場合 [は、][DualScreenAndroidUseEmulator]エミュレーターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="86c18-114">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DualScreenAndroidUseEmulator], restart the emulator.</span></span>  

## <a name="step-2-launch-the-surface-duo-emulator"></a><span data-ttu-id="86c18-115">手順 2: Surface Duo エミュレーターを起動する</span><span class="sxs-lookup"><span data-stu-id="86c18-115">Step 2: Launch the Surface Duo emulator</span></span>  

<span data-ttu-id="86c18-116">Surface [Duo エミュレーターを起動します][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="86c18-116">Launch the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="86c18-117">エミュレーターで実行されている 2 つの異なる画面がエミュレーターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="86c18-117">Notice that the emulator displays 2 different screens running on the emulator.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Duo エミュレーター" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   <span data-ttu-id="86c18-119">Surface Duo エミュレーター</span><span class="sxs-lookup"><span data-stu-id="86c18-119">The Surface Duo emulator</span></span>  
:::image-end:::  

## <a name="step-3-load-your-web-content-in-microsoft-edge-on-the-surface-duo-emulator"></a><span data-ttu-id="86c18-120">手順 3: Surface Duo エミュレーターで Microsoft Edge に Web コンテンツを読み込む</span><span class="sxs-lookup"><span data-stu-id="86c18-120">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span></span>  

<span data-ttu-id="86c18-121">どちらの画面でも [、Surface Duo][DualScreenAndroidUseEmulator] エミュレーターの [お気に入り] トレイを上にスワイプして、[アプリの引き出し] を表示します。</span><span class="sxs-lookup"><span data-stu-id="86c18-121">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DualScreenAndroidUseEmulator] to display the Apps Drawer.</span></span>  <span data-ttu-id="86c18-122">[ **エッジ] を** 選択して [Microsoft Edge アプリを起動します][GooglePlayStoreAppsComMicrosoftEmmx]。</span><span class="sxs-lookup"><span data-stu-id="86c18-122">Choose **Edge** to launch the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Duo エミュレーターの Microsoft Edge アプリ" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   <span data-ttu-id="86c18-124">Surface Duo エミュレーターの Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="86c18-124">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="86c18-125">Microsoft Edge アプリでデバッグする Web サイトまたはアプリ [に移動します][GooglePlayStoreAppsComMicrosoftEmmx]。</span><span class="sxs-lookup"><span data-stu-id="86c18-125">Navigate to the website or app that you want to debug in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

## <a name="step-4-debug-your-web-content-from-the-surface-duo-emulator"></a><span data-ttu-id="86c18-126">手順 4: Surface Duo エミュレーターから Web コンテンツをデバッグする</span><span class="sxs-lookup"><span data-stu-id="86c18-126">Step 4: Debug your web content from the Surface Duo emulator</span></span>  

<span data-ttu-id="86c18-127">Microsoft Edge のデスクトップ インスタンスに切り [替えます][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="86c18-127">Switch back to the desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="86c18-128">このページには、Surface Duo エミュレーターで実行されている開いているタブまたは PWA の一覧が表示された `edge://inspect` **SurfaceDuoEmulator**が[表示されます][DualScreenAndroidUseEmulator]。 [][ProgressiveWebAppsIndex]</span><span class="sxs-lookup"><span data-stu-id="86c18-128">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][ProgressiveWebAppsIndex] that are running on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text="[edge://inspect] ページには、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   <span data-ttu-id="86c18-130">この `edge://inspect` ページには、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="86c18-130">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="86c18-131">**SurfaceDuoEmulator**がページに表示されない場合は、Surface Duo エミュレーターの Microsoft Edge アプリでタブを開くまたは閉 `edge://inspect` [じ直してみてください][DualScreenAndroidUseEmulator]。 [][GooglePlayStoreAppsComMicrosoftEmmx]</span><span class="sxs-lookup"><span data-stu-id="86c18-131">If **SurfaceDuoEmulator** is not displayed on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on the [Surface Duo Emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="86c18-132">その他のトラブルシューティング手順については [、Android デバイスのトラブルシューティング セクションに移動します][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。</span><span class="sxs-lookup"><span data-stu-id="86c18-132">For additional troubleshooting steps, navigate to [troubleshooting section for Android devices][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice].</span></span>  

<span data-ttu-id="86c18-133">エミュレーターで実行されている開いているタブの一覧から、\*\*\*\* デバッグする Web コンテンツを含むタブで [検査] を選択します。</span><span class="sxs-lookup"><span data-stu-id="86c18-133">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span></span>  <span data-ttu-id="86c18-134">Microsoft [Edge DevTools が][DevtoolsIndex] 新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="86c18-134">The [Microsoft Edge DevTools][DevtoolsIndex] will open in a new window.</span></span>  <span data-ttu-id="86c18-135">[ **画面キャストの切り替え** \( 画面キャスト \) の切り替え] を ![ ](../media/toggle-screencast-icon.msft.png) 選択して [、[DevTools]][DualScreenAndroidUseEmulator] ウィンドウで Surface Duo エミュレーターから Web コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="86c18-135">Choose **Toggle Screencast** \(![Toggle Screencast](../media/toggle-screencast-icon.msft.png)\) to view the web content from your [Surface Duo emulator][DualScreenAndroidUseEmulator] in the DevTools window.</span></span>  <span data-ttu-id="86c18-136">これで、Microsoft Edge DevTools を使用して Surface Duo エミュレーターで Web コンテンツを [デバッグできます][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="86c18-136">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="Surface Duo エミュレーターで Microsoft Edge アプリで Microsoft Edge DevTools を使用して Bing をデバッグする" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   <span data-ttu-id="86c18-138">Surface Duo エミュレーターで Microsoft Edge アプリで Microsoft Edge DevTools を使用して Bing をデバッグする</span><span class="sxs-lookup"><span data-stu-id="86c18-138">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="86c18-139">エミュレーターの両方の [画面に Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx] アプリをまたがっている場合、スクリーンキャストはアプリの新しいサイズを反映しますが、ヒンジは反映されません。</span><span class="sxs-lookup"><span data-stu-id="86c18-139">If you span the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span></span>  <span data-ttu-id="86c18-140">ヒンジが Web コンテンツのレイアウトに与える影響を理解するには、スクリーンキャストではなく [Surface Duo エミュレーター][DualScreenAndroidUseEmulator] を使用します。</span><span class="sxs-lookup"><span data-stu-id="86c18-140">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DualScreenAndroidUseEmulator] instead of the screencast.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="86c18-141">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="86c18-141">Additional Resources</span></span>  

<span data-ttu-id="86c18-142">WEB は、HTML、CSS、JavaScript を 1 回書き込み、シングルスクリーン、デュアルスクリーン、および折りたたみ可能なデバイス全体で見た目が良い可能性があるため、折りたたみおよびデュアルスクリーン デバイスの新しいクラスに最適なプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="86c18-142">The web is a great platform for the new class of foldable and dual-screen devices because you may write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span></span>  <span data-ttu-id="86c18-143">詳細については、次の追加リソースに移動して、これらの新しいデバイスの Web コンテンツの構築を開始します。</span><span class="sxs-lookup"><span data-stu-id="86c18-143">For more information, navigate to the following additional resources to get started building web content for these new devices.</span></span>  

*   [<span data-ttu-id="86c18-144">デュアルスクリーン デバイスでアプリを作成するためのドキュメント</span><span class="sxs-lookup"><span data-stu-id="86c18-144">Documentation for creating apps on dual-screen devices</span></span>][DualScreenIndex]  
*   [<span data-ttu-id="86c18-145">折りたたみおよびデュアルスクリーン デバイスで Web エクスペリエンスを構築するための新しい API の Microsoft Edge Web プラットフォームの説明者</span><span class="sxs-lookup"><span data-stu-id="86c18-145">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span></span>][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [<span data-ttu-id="86c18-146">Microsoft 365 Developer Day セッションの記録: Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する方法</span><span class="sxs-lookup"><span data-stu-id="86c18-146">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span></span>][YoutubeDxrzwsqxpvc]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="86c18-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="86c18-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows 上のプログレッシブ Web アプリ |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "トラブルシューティング: DevTools が Android デバイスを検出していない - Android デバイスのリモート デバッグを開始する方法|Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "デュアルスクリーン デバイス向けアプリを作成|Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface DUo エミュレーターを使用|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo SDK を取得|Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge の導入"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo の新しい|Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface Duo SDK プレビュー リリース のダウンロード |Microsoft ダウンロード センター"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge: Web ブラウザー |GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ可能なデバイスでの啓蒙エクスペリエンスのための Web プラットフォーム プリミティブ - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する|YouTube"  
