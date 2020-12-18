---
description: Surface Emulator エミュレーターのリモート デバッグを開始します。
title: Surface Emulator エミュレーターのリモート デバッグの開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, Web 開発, f12 ツール, devtools, リモート デバッグ, android, surface の数
ms.openlocfilehash: f44c85c468de3bdd7727695e3f33269584966231
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230647"
---
# <span data-ttu-id="9cd00-104">Surface Emulator エミュレーターのリモート デバッグの開始</span><span class="sxs-lookup"><span data-stu-id="9cd00-104">Get Started with Remote Debugging Surface Duo emulators</span></span>  

<span data-ttu-id="9cd00-105">この記事では[、Microsoft Edge][MicrosoftSurfaceDevicesSurfaceDuo]のデスクトップ インスタンスから Surface Emulator の[Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx]アプリで Web コンテンツをリモートでデバッグするプロセスについて[説明します][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-105">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on a [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo] emulator from a desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="9cd00-106">Surface Duo デバイスでのデバッグの詳細については、Android デバイスのリモート デバッグに関する [ガイドに従ってください][DevtoolsRemoteDebuggingMain]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-106">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][DevtoolsRemoteDebuggingMain].</span></span>  

## <span data-ttu-id="9cd00-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="9cd00-107">Before you Begin</span></span>

<span data-ttu-id="9cd00-108">Surface Emulator エミュレーター [を実行する][MicrosoftDownload100847] 前に [、Surface Sdk をインストールします][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-108">Install the [Surface Duo SDK][MicrosoftDownload100847] before running the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="9cd00-109">詳しくは [、Surface Sdk の取得に関するページをご覧ください][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-109">For more information, see [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

## <span data-ttu-id="9cd00-110">手順 1: フォルダーに移動edge://inspect</span><span class="sxs-lookup"><span data-stu-id="9cd00-110">Step 1: Navigate to edge://inspect</span></span>  

<span data-ttu-id="9cd00-111">Microsoft Edge のデスクトップ インスタンス [を開き][MicrosoftEdge]、次に移動します `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="9cd00-111">Open a desktop instance of [Microsoft Edge][MicrosoftEdge], and navigate to `edge://inspect`.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="デスクトップedge://inspect Microsoft Edge のページ" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   <span data-ttu-id="9cd00-113">デスクトップ `edge://inspect` 上の Microsoft Edge のページ</span><span class="sxs-lookup"><span data-stu-id="9cd00-113">The `edge://inspect` page in Microsoft Edge on the desktop</span></span>  
:::image-end:::

> [!NOTE]
> <span data-ttu-id="9cd00-114">ページで `edge://inspect` Surface Emulator エミュレーターが認識されない場合 [は、][DualScreenAndroidUseEmulator]エミュレーターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9cd00-114">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DualScreenAndroidUseEmulator], restart the emulator.</span></span>  

## <span data-ttu-id="9cd00-115">手順 2: Surface Emulator エミュレーターを起動する</span><span class="sxs-lookup"><span data-stu-id="9cd00-115">Step 2: Launch the Surface Duo emulator</span></span>  

<span data-ttu-id="9cd00-116">Surface [Emulator エミュレーターを起動します][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-116">Launch the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="9cd00-117">エミュレーターで実行されている 2 つの異なる画面がエミュレーターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cd00-117">Notice that the emulator displays 2 different screens running on the emulator.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Emulator" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   <span data-ttu-id="9cd00-119">Surface Emulator</span><span class="sxs-lookup"><span data-stu-id="9cd00-119">The Surface Duo emulator</span></span>  
:::image-end:::  

## <span data-ttu-id="9cd00-120">手順 3: Surface Emulator エミュレーターで Microsoft Edge に Web コンテンツを読み込む</span><span class="sxs-lookup"><span data-stu-id="9cd00-120">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span></span>  

<span data-ttu-id="9cd00-121">どちらの画面でも [、Surface Emulator][DualScreenAndroidUseEmulator] エミュレーターのお気に入りトレイを上にスワイプして、アプリ ドロワーを表示します。</span><span class="sxs-lookup"><span data-stu-id="9cd00-121">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DualScreenAndroidUseEmulator] to display the Apps Drawer.</span></span>  <span data-ttu-id="9cd00-122">**[Edge] を**選択して[Microsoft Edge アプリを起動します][GooglePlayStoreAppsComMicrosoftEmmx]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-122">Choose **Edge** to launch the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Emulator エミュレーター上の Microsoft Edge アプリ" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   <span data-ttu-id="9cd00-124">Surface Emulator エミュレーター上の Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="9cd00-124">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="9cd00-125">Microsoft Edge アプリでデバッグする Web サイトまたはアプリに [移動します][GooglePlayStoreAppsComMicrosoftEmmx]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-125">Navigate to the website or app that you want to debug in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

## <span data-ttu-id="9cd00-126">手順 4: Surface Emulator エミュレーターから Web コンテンツをデバッグする</span><span class="sxs-lookup"><span data-stu-id="9cd00-126">Step 4: Debug your web content from the Surface Duo emulator</span></span>  

<span data-ttu-id="9cd00-127">Microsoft Edge のデスクトップ インスタンスに切り [替えます][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-127">Switch back to the desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="9cd00-128">このページには、Surface Emulator エミュレーターで実行されている開いているタブまたは PAS の一覧が表示された `edge://inspect` [][ProgressiveWebAppsIndex]**SurfaceDwrEmulator** [が表示されます][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-128">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][ProgressiveWebAppsIndex] that are running on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text="次edge://inspect、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   <span data-ttu-id="9cd00-130">この `edge://inspect` ページには、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cd00-130">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="9cd00-131">ページに**SurfaceD emulatorEmulator**が表示されない場合は、Surface Emulator エミュレーターの Microsoft Edge アプリでタブを開くまたは閉 `edge://inspect` [じしてみてください][DualScreenAndroidUseEmulator]。 [][GooglePlayStoreAppsComMicrosoftEmmx]</span><span class="sxs-lookup"><span data-stu-id="9cd00-131">If you do not see **SurfaceDuoEmulator** on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on the [Surface Duo Emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="9cd00-132">その他のトラブルシューティング手順については [、Android デバイスのトラブルシューティングのセクションを参照してください][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-132">For additional troubleshooting steps, see the [troubleshooting section for Android devices][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice].</span></span>  

<span data-ttu-id="9cd00-133">エミュレーターで実行されている開いているタブの一覧から、\*\*\*\* デバッグする Web コンテンツを含むタブの検査を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd00-133">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span></span>  <span data-ttu-id="9cd00-134">Microsoft [Edge DevTools が][DevtoolsIndex] 新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="9cd00-134">The [Microsoft Edge DevTools][DevtoolsIndex] will open in a new window.</span></span>  <span data-ttu-id="9cd00-135">[Toggle **Screencast** \( Toggle Screencast \) ] を選択して、Surface Emulator エミュレーターの Web コンテンツを ![ ][ImageToggleScreencastIcon] DevTools ウィンドウに表示します。 [][DualScreenAndroidUseEmulator]</span><span class="sxs-lookup"><span data-stu-id="9cd00-135">Choose **Toggle Screencast** \(![Toggle Screencast][ImageToggleScreencastIcon]\) to view the web content from your [Surface Duo emulator][DualScreenAndroidUseEmulator] in the DevTools window.</span></span>  <span data-ttu-id="9cd00-136">これで、Microsoft Edge DevTools を使用して、Surface Emulator エミュレーターで Web コンテンツ [をデバッグできます][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="9cd00-136">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="Microsoft Edge DevTools を使用して Surface Emulator エミュレーター上の Microsoft Edge アプリで Bing をデバッグする" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   <span data-ttu-id="9cd00-138">Microsoft Edge DevTools を使用して Surface Emulator エミュレーター上の Microsoft Edge アプリで Bing をデバッグする</span><span class="sxs-lookup"><span data-stu-id="9cd00-138">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="9cd00-139">エミュレーターの両方の画面 [に Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx] アプリをまたがっている場合、スクリーンキャストにはアプリの新しいサイズが反映されますが、画面は反映されません。</span><span class="sxs-lookup"><span data-stu-id="9cd00-139">If you span the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span></span>  <span data-ttu-id="9cd00-140">この問題が Web コンテンツのレイアウトに与える影響を理解するには、スクリーンキャストの代わりに [Surface Emulator][DualScreenAndroidUseEmulator] エミュレーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9cd00-140">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DualScreenAndroidUseEmulator] instead of the screencast.</span></span>  

## <span data-ttu-id="9cd00-141">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="9cd00-141">Additional Resources</span></span>  

<span data-ttu-id="9cd00-142">この Web は、HTML、CSS、JavaScript を 1 回記述して、単一画面、デュアルスクリーン、折りたたみ可能なデバイスで見た目が良いため、折りたたみ可能なデュアルスクリーン デバイスの新しいクラスに最適なプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="9cd00-142">The web is a great platform for the new class of foldable and dual-screen devices because you can write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span></span>  <span data-ttu-id="9cd00-143">詳細については、これらの新しいデバイスの Web コンテンツの構築を開始するために、以下のその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd00-143">For more information, see these additional resources to get started building web content for these new devices.</span></span>  

*   [<span data-ttu-id="9cd00-144">デュアルスクリーン デバイスでアプリを作成するためのドキュメント</span><span class="sxs-lookup"><span data-stu-id="9cd00-144">Documentation for creating apps on dual-screen devices</span></span>][DualScreenIndex]  
*   [<span data-ttu-id="9cd00-145">折りたたみ可能なデュアルスクリーン デバイスで Web エクスペリエンスを構築するための新しい API に関する Microsoft Edge Web プラットフォームの説明</span><span class="sxs-lookup"><span data-stu-id="9cd00-145">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span></span>][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [<span data-ttu-id="9cd00-146">Microsoft 365 Developer Day セッションのレコーディング: Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する方法</span><span class="sxs-lookup"><span data-stu-id="9cd00-146">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span></span>][YoutubeDxrzwsqxpvc]  

<!-- image links -->  

[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows での段階的な Web アプリ |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "Android デバイスのリモート デバッグの概要 |Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "トラブルシューティング: DevTools が Android デバイスを検出しない - Android デバイスのリモート デバッグの概要 |Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "デュアルスクリーン デバイス用のアプリを作成する |Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface D Emulator を使う |Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Sdk を取得する |Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge の導入"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface の組み合わせ |Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface Sdk プレビュー リリースをダウンロードする |Microsoft ダウンロード センター"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge: Web ブラウザー |GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ可能なデバイスでの対応エクスペリエンスのための Web プラットフォーム プリミティブ - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する方法 |YouTube"  
