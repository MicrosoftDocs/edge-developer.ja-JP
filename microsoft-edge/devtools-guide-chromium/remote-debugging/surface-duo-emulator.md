---
title: リモートデバッグ Surface Duo エミュレーターの使用を開始する
author: zoherghadyali
ms.author: zoghadya
ms.date: 04/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、リモートデバッグ、android、surface duo
ms.openlocfilehash: af6fa6433b0bc6bba0599e6e9a805235504caadd
ms.sourcegitcommit: 966bfc60040acc794b6ee20eb2084bc8264a4852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "10621503"
---
# <span data-ttu-id="cc8e3-103">リモートデバッグ Surface Duo エミュレーターの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="cc8e3-103">Get Started with Remote Debugging Surface Duo emulators</span></span>

<span data-ttu-id="cc8e3-104">この記事では、 [microsoft][DesktopEdge]edge のデスクトップインスタンスから[Surface Duo][SurfaceDuo]エミュレーター上の[microsoft edge アプリ][AndroidEdge]の web コンテンツをリモートでデバッグするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-104">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][AndroidEdge] on a [Surface Duo][SurfaceDuo] emulator from a desktop instance of [Microsoft Edge][DesktopEdge].</span></span> <span data-ttu-id="cc8e3-105">Surface Duo デバイスでのデバッグについては、「 [Android デバイスのリモートデバッグ][RemoteDebuggingAndroid]のガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-105">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][RemoteDebuggingAndroid].</span></span>

## <span data-ttu-id="cc8e3-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="cc8e3-106">Before you Begin</span></span>

<span data-ttu-id="cc8e3-107">Surface [duo エミュレーター][DuoEmulator]を実行する前に[surface duo SDK][DuoSdk]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-107">Install the [Surface Duo SDK][DuoSdk] before running the [Surface Duo emulator][DuoEmulator].</span></span> <span data-ttu-id="cc8e3-108">詳しくは、「 [Surface DUO SDK の入手][DuoSdkdocs]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-108">For more information, see [Get the Surface Duo SDK][DuoSdkdocs].</span></span>

## <span data-ttu-id="cc8e3-109">手順 1: edge://inspect に移動する</span><span class="sxs-lookup"><span data-stu-id="cc8e3-109">Step 1: Navigate to edge://inspect</span></span>

<span data-ttu-id="cc8e3-110">[Microsoft Edge][DesktopEdge]のデスクトップインスタンスを開き、に移動し `edge://inspect` ます。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-110">Open a desktop instance of [Microsoft Edge][DesktopEdge], and navigate to `edge://inspect`.</span></span>

> ##### <span data-ttu-id="cc8e3-111">図 1</span><span class="sxs-lookup"><span data-stu-id="cc8e3-111">Figure 1</span></span>  
> <span data-ttu-id="cc8e3-112">デスクトップ `edge://inspect` 上の Microsoft edge のページデスクトップ上の ![ microsoft edge の edge://inspect ページ][ImageEdgeInspect]</span><span class="sxs-lookup"><span data-stu-id="cc8e3-112">The `edge://inspect` page in Microsoft Edge on the desktop ![The edge://inspect page in Microsoft Edge on the desktop][ImageEdgeInspect]</span></span>

> [!NOTE]
> <span data-ttu-id="cc8e3-113">ページで `edge://inspect` [Surface Duo エミュレーター][DuoEmulator]が認識されない場合は、エミュレーターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-113">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DuoEmulator], restart the emulator.</span></span>

## <span data-ttu-id="cc8e3-114">手順 2: Surface Duo エミュレーターを起動する</span><span class="sxs-lookup"><span data-stu-id="cc8e3-114">Step 2: Launch the Surface Duo emulator</span></span>

<span data-ttu-id="cc8e3-115">[Surface Duo エミュレーター][DuoEmulator]を起動します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-115">Launch the [Surface Duo emulator][DuoEmulator].</span></span> <span data-ttu-id="cc8e3-116">エミュレーターでは、2つの異なる画面がエミュレーターで実行されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-116">Notice that the emulator displays 2 different screens running on the emulator.</span></span>

> ##### <span data-ttu-id="cc8e3-117">図 2</span><span class="sxs-lookup"><span data-stu-id="cc8e3-117">Figure 2</span></span>
> <span data-ttu-id="cc8e3-118">Surface duo エミュレーター ![ の Surface duo エミュレーター][ImageDuoEmulator]</span><span class="sxs-lookup"><span data-stu-id="cc8e3-118">The Surface Duo emulator ![The Surface Duo emulator][ImageDuoEmulator]</span></span>  

## <span data-ttu-id="cc8e3-119">手順 3: Surface Duo エミュレーターで Microsoft Edge に web コンテンツを読み込む</span><span class="sxs-lookup"><span data-stu-id="cc8e3-119">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span></span>

<span data-ttu-id="cc8e3-120">どちらの画面でも、 [Surface Duo エミュレーター][DuoEmulator]のお気に入りトレイを上にスワイプして、[アプリ] ドローワを表示します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-120">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DuoEmulator] to display the Apps Drawer.</span></span> <span data-ttu-id="cc8e3-121">[ **Edge** ] を選択して、 [Microsoft edge アプリ][AndroidEdge]を起動します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-121">Choose **Edge** to launch the [Microsoft Edge app][AndroidEdge].</span></span>

> ##### <span data-ttu-id="cc8e3-122">図 3</span><span class="sxs-lookup"><span data-stu-id="cc8e3-122">Figure 3</span></span>
> <span data-ttu-id="cc8e3-123">Surface duo エミュレーター上の Microsoft edge アプリ (surface duo エミュレーター上の microsoft edge ![ アプリ)][ImageDuoEmulatorEdge]</span><span class="sxs-lookup"><span data-stu-id="cc8e3-123">The Microsoft Edge app on the Surface Duo emulator ![The Microsoft Edge app on the Surface Duo emulator][ImageDuoEmulatorEdge]</span></span>  

<span data-ttu-id="cc8e3-124">[Microsoft Edge アプリ][AndroidEdge]でデバッグする web サイトまたはアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-124">Navigate to the website or app that you want to debug in the [Microsoft Edge app][AndroidEdge].</span></span>

## <span data-ttu-id="cc8e3-125">手順 4: Surface Duo エミュレーターから web コンテンツをデバッグする</span><span class="sxs-lookup"><span data-stu-id="cc8e3-125">Step 4: Debug your web content from the Surface Duo emulator</span></span> 

<span data-ttu-id="cc8e3-126">[Microsoft Edge][DesktopEdge]のデスクトップインスタンスに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-126">Switch back to the desktop instance of [Microsoft Edge][DesktopEdge].</span></span> <span data-ttu-id="cc8e3-127">この `edge://inspect` ページには、 [Surface Duo エミュレーター][DuoEmulator]で実行されている、開いているタブまたは[pwas][PwaDocs]の一覧が表示された**SurfaceDuoEmulator**が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-127">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaDocs] that are running on the [Surface Duo emulator][DuoEmulator].</span></span>

> ##### <span data-ttu-id="cc8e3-128">図 4</span><span class="sxs-lookup"><span data-stu-id="cc8e3-128">Figure 4</span></span>
> <span data-ttu-id="cc8e3-129">このページには、 `edge://inspect` エミュレーターで実行されている Microsoft edge アプリの開いているタブの一覧が表示され ![ ます。 Edge://inspect ページには、エミュレーターで実行されている microsoft edge アプリの開いているタブの一覧が表示されます。][ImageEdgeInspectTargets]</span><span class="sxs-lookup"><span data-stu-id="cc8e3-129">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator ![The edge://inspect page displays a list of the open tabs in the Microsoft Edge app running on the emulator][ImageEdgeInspectTargets]</span></span>  

> [!NOTE]
> <span data-ttu-id="cc8e3-130">ページに**SurfaceDuoEmulator**が表示されない場合は `edge://inspect` 、 [Surface Duo エミュレーター][DuoEmulator]で[Microsoft Edge アプリ][AndroidEdge]のタブを開くか、または閉じてみてください。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-130">If you do not see **SurfaceDuoEmulator** on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][AndroidEdge] on the [Surface Duo Emulator][DuoEmulator].</span></span> <span data-ttu-id="cc8e3-131">その他のトラブルシューティング手順については、「 [Android デバイスのトラブルシューティング」][TroubleshootingAndroid]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-131">For additional troubleshooting steps, see the [troubleshooting section for Android devices][TroubleshootingAndroid].</span></span>

<span data-ttu-id="cc8e3-132">エミュレーターで実行されている開いているタブの一覧から、デバッグする web コンテンツがあるタブで [**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-132">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span></span> <span data-ttu-id="cc8e3-133">[Microsoft Edge DevTools][DevToolsDocs]が新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-133">The [Microsoft Edge DevTools][DevToolsDocs] will open in a new window.</span></span> <span data-ttu-id="cc8e3-134">「ツール」「**切り替え Screencast** ![ トグル Screencast を選択して ][ImageToggleScreencastIcon] 、「Devtools」ウィンドウで[Surface Duo エミュレーター][DuoEmulator]の web コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-134">Choose **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] to view the web content from your [Surface Duo emulator][DuoEmulator] in the DevTools window.</span></span> <span data-ttu-id="cc8e3-135">[Surface Duo エミュレーター][DuoEmulator]で、Microsoft Edge devtools を使って web コンテンツをデバッグできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-135">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DuoEmulator].</span></span>

> ##### <span data-ttu-id="cc8e3-136">図 5</span><span class="sxs-lookup"><span data-stu-id="cc8e3-136">Figure 5</span></span>
> <span data-ttu-id="cc8e3-137">Microsoft edge DevTools を使って Surface Duo エミュレーター上の Microsoft Edge アプリで Bing をデバッグします。 ![ surface duo エミュレーター上の Microsoft edge アプリで bing をデバッグします。][ImageDevTools]</span><span class="sxs-lookup"><span data-stu-id="cc8e3-137">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator ![Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator][ImageDevTools]</span></span>  

> [!NOTE]
> <span data-ttu-id="cc8e3-138">エミュレーターの両方の画面で[Microsoft Edge アプリ][AndroidEdge]をスパンしている場合、screencast には、アプリケーションの新しいサイズが反映されますが、ヒンジは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-138">If you span the [Microsoft Edge app][AndroidEdge] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span></span> <span data-ttu-id="cc8e3-139">ヒンジが web コンテンツのレイアウトに与える影響を理解するには、screencast ではなく[Surface Duo エミュレーター][DuoEmulator]を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-139">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DuoEmulator] instead of the screencast.</span></span>

## <span data-ttu-id="cc8e3-140">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="cc8e3-140">Additional Resources</span></span>

<span data-ttu-id="cc8e3-141">Web は、HTML、CSS、JavaScript を1回作成でき、1画面、2画面、折りたたみ式デバイスで適切に表示されるようにするため、折りたたみ式とデュアルスクリーンデバイスの新しいクラスの優れたプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-141">The web is a great platform for the new class of foldable and dual-screen devices because you can write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span></span> <span data-ttu-id="cc8e3-142">詳細については、以下の追加リソースを参照してください。これらの新しいデバイスの web コンテンツの構築を開始します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-142">For more information, see these additional resources to get started building web content for these new devices.</span></span>

- [<span data-ttu-id="cc8e3-143">デュアルスクリーンデバイスでのアプリの作成に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="cc8e3-143">Documentation for creating apps on dual-screen devices</span></span>][DualScreenDocs]
- [<span data-ttu-id="cc8e3-144">Microsoft Edge web platform explainer は、新しい Api を使用して、折りたたみ式デバイスとデュアルスクリーンデバイスで web エクスペリエンスを構築します。</span><span class="sxs-lookup"><span data-stu-id="cc8e3-144">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span></span>][WebPlatformExplainer]
- [<span data-ttu-id="cc8e3-145">Microsoft 365 Developer Day セッションの記録: web サイトと web アプリのためのデュアルスクリーンエクスペリエンスの構築方法</span><span class="sxs-lookup"><span data-stu-id="cc8e3-145">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span></span>][DeveloperDay]

<!-- image links -->  
[ImageEdgeInspect]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page.msft.png "図 1: デスクトップ上の Microsoft Edge の edge://inspect ページ"
[ImageDuoEmulator]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator.msft.png "図 2: Surface Duo エミュレーター"
[ImageDuoEmulatorEdge]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator-edge.msft.png "図 3: Surface Duo エミュレーター上の Microsoft Edge アプリ"
[ImageEdgeInspectTargets]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png "図 4: edge://inspect ページには、エミュレーターで実行されている Microsoft Edge アプリの開いているタブの一覧が表示されます。"
[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png
[ImageDevTools]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-devtools.msft.png "図 5: Surface Duo エミュレーター上の Microsoft Edge アプリで Bing をデバッグするための Microsoft Edge DevTools の使用"

<!-- links -->  
[RemoteDebuggingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Android デバイスのリモートデバッグの概要"
[PwaDocs]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ"
[DevToolsDocs]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"
[TroubleshootingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index#troubleshooting-devtools-is-not-detecting-the-android-device "トラブルシューティング: DevTools で Android デバイスが検出されない"

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android アプリ"
[SurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo の概要"
[DesktopEdge]: https://www.microsoft.com/edge/ "新しい Microsoft Edge の紹介"
[DuoEmulator]: https://docs.microsoft.com/dual-screen/android/use-emulator "Surface DUo エミュレーターを使う"
[DuoSdk]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface Duo SDK Preview リリース"
[DuoSdkDocs]: https://docs.microsoft.com/dual-screen/android/get-duo-sdk "Surface Duo SDK の入手"
[DualScreenDocs]: https://docs.microsoft.com/dual-screen/ "デュアルスクリーンデバイス用のアプリを作成する"
[WebPlatformExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ式デバイスでの対応エクスペリエンスのための Web Platform プリミティブ"
[DeveloperDay]: https://youtu.be/DXrZWsqXPVc "Web サイトと web アプリのためのデュアルスクリーンエクスペリエンスを構築する方法"
