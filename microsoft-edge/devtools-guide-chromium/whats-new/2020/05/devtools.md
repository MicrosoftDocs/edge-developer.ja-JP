---
title: DevTools の新機能 (Microsoft Edge 84)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fc5dcc10ba3a79bd3f073e0e3504e551d7e23d70
ms.sourcegitcommit: ba9f0ed77e84174b03262b17e62c6a7e26cfeb3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2020
ms.locfileid: "10688179"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="6bf42-103">DevTools の新機能 (Microsoft Edge 84)</span><span class="sxs-lookup"><span data-stu-id="6bf42-103">What's new in DevTools (Microsoft Edge 84)</span></span>  

## <span data-ttu-id="6bf42-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="6bf42-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="6bf42-105">以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="6bf42-106">これらを確認して、DevTools、VS コード拡張などの新機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="6bf42-107">開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels]をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="6bf42-108">Windows のハイコントラストモードで DevTools を使う</span><span class="sxs-lookup"><span data-stu-id="6bf42-108">Use the DevTools in Windows high contrast mode</span></span>

<span data-ttu-id="6bf42-109">Windows がハイコントラストモードの場合は、Microsoft Edge DevTools がハイコントラストモードで表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-109">The Microsoft Edge DevTools are now displayed in high contrast mode when Windows is in high contrast mode.</span></span>  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="ハイコントラストモードの Microsoft Edge DevTools" lightbox="../../media/2020/05/high-contrast.msft.png":::
   <span data-ttu-id="6bf42-111">ハイコントラストモードの Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="6bf42-111">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-112">[指示に従って、Windows でハイコントラストモードをオン][MicrosoftSupportWindows10HighContrastMode]にします。</span><span class="sxs-lookup"><span data-stu-id="6bf42-112">[Follow the instructions to turn on high contrast mode in Windows][MicrosoftSupportWindows10HighContrastMode].</span></span>  <span data-ttu-id="6bf42-113">またはを押して、Microsoft Edge で DevTools を開き `F12` `Ctrl` + `Shift` + `I` ます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-113">Open the DevTools in Microsoft Edge by pressing `F12` or `Ctrl`+`Shift`+`I`.</span></span>  <span data-ttu-id="6bf42-114">DevTools はハイコントラストモードで表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-114">The DevTools are displayed in high contrast mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="6bf42-115">Microsoft Edge DevTools は現在、macOS ではサポートされていませんが、Windows のハイコントラストモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6bf42-115">The Microsoft Edge DevTools currently support high contrast mode on Windows but not on macOS.</span></span> 

<span data-ttu-id="6bf42-116">Chromium の問題[#1048378][CR1048378]</span><span class="sxs-lookup"><span data-stu-id="6bf42-116">Chromium issue [#1048378][CR1048378]</span></span>  

### <span data-ttu-id="6bf42-117">開発ツールのキーボードショートカットを VS コードに一致させる</span><span class="sxs-lookup"><span data-stu-id="6bf42-117">Match keyboard shortcuts in the DevTools to VS Code</span></span>  

<span data-ttu-id="6bf42-118">[フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)と[Chromium の公開問題の追跡][CRIssuesList]ツールでは、Microsoft Edge DevTools チームが、devtools でキーボードショートカットをカスタマイズする機能が必要であることを学習しました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-118">From your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) and the [Chromium public issue tracker][CRIssuesList], the Microsoft Edge DevTools team learned that you wanted the ability to customize keyboard shortcuts in the DevTools.</span></span>  <span data-ttu-id="6bf42-119">Microsoft Edge 84 では、DevTools のキーボードショートカットを、ショートカットのカスタマイズについてチームが作業している機能の1つである[VS コード][VSCode]に一致させることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-119">In Microsoft Edge 84, you are now able to match keyboard shortcuts in the DevTools to [VS Code][VSCode], which is just one of the features the team is working on for shortcut customization.</span></span>  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="開発ツールのキーボードショートカットを VS コードに一致させる" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   <span data-ttu-id="6bf42-121">ハイコントラストモードの Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="6bf42-121">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-122">実験を試みるには、devtools `?` ![ ][ImageSettingsIcon] の右上隅にある [devtools の設定] アイコンをクリックまたは選択して、Devtools の設定を開きます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-122">To try the experiment, open DevTools Settings by pressing `?` or selecting the ![DevTools Settings icon][ImageSettingsIcon] icon in the top-right corner of the DevTools.</span></span>  <span data-ttu-id="6bf42-123">[**実験**] セクションに移動し、[ユーザー設定の**キーボードショートカットを有効にする] をオンにします (再読み込みが必要)**。</span><span class="sxs-lookup"><span data-stu-id="6bf42-123">Navigate to the **Experiments** section and check **Enable custom keyboard shortcuts settings tab (requires reload)**.</span></span>  <span data-ttu-id="6bf42-124">次に、DevTools を再読み込みし、設定をもう一度開き、[**ショートカット**] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-124">Now reload the DevTools, open Settings again, and navigate to the **Shortcuts** section.</span></span>  

<span data-ttu-id="6bf42-125">[**標準のショートカットキー**の選択] ドロップダウンで [ **Devtools (既定値)** ] を選び、[ **Visual Studio コード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-125">Select **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="6bf42-126">DevTools のキーボードショートカットは、VS コードで同等のアクションのショートカットと一致するようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-126">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in VS Code.</span></span>  

<span data-ttu-id="6bf42-127">たとえば、 [VS コード][VSCodeShortcuts]でスクリプトを一時停止または実行し続けるためのキーボードショートカットは、 `F5` です。</span><span class="sxs-lookup"><span data-stu-id="6bf42-127">For example, the keyboard shortcut for pausing or continuing running a script in [VS Code][VSCodeShortcuts] is `F5`.</span></span>  <span data-ttu-id="6bf42-128">**Devtools (既定)** の事前設定を使用すると、devtools の同じショートカットが `F8` **Visual Studio のコード**プリセットでも使用できるようになりました `F5` 。</span><span class="sxs-lookup"><span data-stu-id="6bf42-128">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8` but with the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="6bf42-129">この機能は、現在 Microsoft Edge 84 で実験として提供されているので、チームと[フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)を共有してください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-129">The feature is currently available in Microsoft Edge 84 as an experiment, so please share your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) with the team!</span></span>  

<span data-ttu-id="6bf42-130">Chromium の問題[#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="6bf42-130">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="6bf42-131">リモートデバッグ Surface Duo エミュレーター</span><span class="sxs-lookup"><span data-stu-id="6bf42-131">Remote debug Surface Duo emulators</span></span>  

<span data-ttu-id="6bf42-132">[Microsoft Edge DevTools][DevToolsChromiumGuide]の全機能を使用して、 [Surface Duo エミュレーター][DualScreensAndroidEmulator]で実行されている web コンテンツをリモートでデバッグできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-132">You are now able to remotely debug your web content running in the [Surface Duo emulator][DualScreensAndroidEmulator] using the full power of the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

<span data-ttu-id="6bf42-133">[Surface Duo エミュレーター][DualScreensAndroidEmulator]を使用すると、折りたたみ式とデュアルスクリーンデバイスの新しいクラスで web コンテンツがどのようにレンダリングされるかをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-133">With the [Surface Duo emulator][DualScreensAndroidEmulator], you are able to test how your web content renders on a new class of foldable and dual-screen devices.</span></span>  <span data-ttu-id="6bf42-134">エミュレーターは Android オペレーティングシステムを実行し、 [Microsoft Edge Android アプリ][AndroidEdge]を提供します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-134">The emulator runs the Android operating system and provides the [Microsoft Edge Android app][AndroidEdge].</span></span>  <span data-ttu-id="6bf42-135">[Microsoft edge アプリ][AndroidEdge]で web コンテンツを読み込み、 [Microsoft edge devtools][DevToolsChromiumGuide]を使ってデバッグします。</span><span class="sxs-lookup"><span data-stu-id="6bf42-135">Load your web content in the [Microsoft Edge app][AndroidEdge] and debug it with the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="Surface Duo エミュレーターで実行されている Microsoft Edge アプリ" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   <span data-ttu-id="6bf42-137">Surface Duo エミュレーター上の Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="6bf42-137">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-138">`edge://inspect` [Microsoft Edge][DesktopEdge]のデスクトップインスタンスのページには、 [Surface Duo エミュレーター][DualScreensAndroidEmulator]で実行されている開いているタブまたは[pwas][PwaIndex]の一覧が表示された**SurfaceDuoEmulator**が示されています。</span><span class="sxs-lookup"><span data-stu-id="6bf42-138">The `edge://inspect` page in a desktop instance of [Microsoft Edge][DesktopEdge] shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaIndex] that are running on the [Surface Duo emulator][DualScreensAndroidEmulator].</span></span>  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="Edge://inspect ページには、エミュレーターで実行されている Microsoft Edge アプリの開いているタブの一覧が表示されます。" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   <span data-ttu-id="6bf42-140">このページには、 `edge://inspect` エミュレーターで実行されている Microsoft Edge アプリの開いているタブの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-140">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>
:::image-end:::  

<span data-ttu-id="6bf42-141">デバッグするタブまたは PWA の [**検査**] を選ぶと、 [Microsoft Edge devtools][DevToolsChromiumGuide]が開きます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-141">Selecting **inspect** for the tab or PWA that you want to debug opens the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  <span data-ttu-id="6bf42-142">[次のステップバイステップガイドを参照して、Surface Duo エミュレーターで web コンテンツをリモートでデバッグ][DevToolsRemoteDebugDuoEmulator]します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-142">[Follow the step-by-step guide to remotely debug your web content on the Surface Duo emulator][DevToolsRemoteDebugDuoEmulator].</span></span>  

### <span data-ttu-id="6bf42-143">DevTools のドローワのサイズをより簡単に変更する</span><span class="sxs-lookup"><span data-stu-id="6bf42-143">Resize the DevTools drawer more easily</span></span>  

<span data-ttu-id="6bf42-144">Microsoft Edge 83 以前のバージョンでは、ドロアーのツールバー内にマウスポインターを置くことによって、 [Devtools の引き出し][DevToolsDrawer]のサイズを変更することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="6bf42-144">In Microsoft Edge 83 or earlier, you were only able to resize the [DevTools Drawer][DevToolsDrawer] by hovering inside the Drawer's toolbar.</span></span>  <span data-ttu-id="6bf42-145">ドロワーの動作は、ウィンドウの枠線をポイントしてサイズを変更する DevTools のウィンドウの他のサイズ変更コントロールとは異なります。</span><span class="sxs-lookup"><span data-stu-id="6bf42-145">The Drawer behaved differently than the other resize controls for panes in the DevTools where you hover over the border of the pane to resize it.</span></span>  <span data-ttu-id="6bf42-146">次の画像を選択して、Microsoft Edge のバージョン83またはそれ以前のドロアーのサイズ変更の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-146">Select the following image to see how resizing the Drawer worked in version 83 or earlier of Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="Microsoft Edge 83 の DevTools の引き出しのサイズ変更" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   <span data-ttu-id="6bf42-148">Microsoft Edge 83 の DevTools の引き出しのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="6bf42-148">Resizing the DevTools Drawer in Microsoft Edge 83</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="6bf42-149">Microsoft Edge 84 以降では、ドロアーの境界線の上にマウスポインターを置くと、引き出しのサイズを変更できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-149">Starting with Microsoft Edge 84, you are now able to resize the Drawer by hovering over the border of the Drawer.</span></span>  <span data-ttu-id="6bf42-150">この変更によって、devtools の他のペインのサイズを変更する方法で、DevTools のドローワのサイズ変更動作が揃えられます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-150">This change aligns the behavior resizing the DevTools Drawer with the way you resize other panes in the DevTools.</span></span>  <span data-ttu-id="6bf42-151">Microsoft Edge 84 でのサイズ変更の動作を確認するには、次の画像を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-151">Select the following image to see resizing in action in Microsoft Edge 84.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="Microsoft Edge 84 の DevTools の引き出しのサイズ変更" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   <span data-ttu-id="6bf42-153">Microsoft Edge 84 の DevTools の引き出しのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="6bf42-153">Resizing the DevTools Drawer in Microsoft Edge 84</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="6bf42-154">Chromium の問題[#1076112][CR1076112]</span><span class="sxs-lookup"><span data-stu-id="6bf42-154">Chromium issue [#1076112][CR1076112]</span></span>  

### <span data-ttu-id="6bf42-155">Screencasting ナビゲーションボタンにフォーカスが表示</span><span class="sxs-lookup"><span data-stu-id="6bf42-155">Screencasting navigation buttons display focus</span></span>  

<span data-ttu-id="6bf42-156">[Android デバイス][DevToolsRemoteDebugAndroid]、 [Windows 10 デバイス][DevToolsRemoteDebugWindows]、 [Surface Duo エミュレーター][DevToolsRemoteDebugDuoEmulator]をリモートでデバッグしている場合、 ![ ][ImageScreencastingIcon] Devtools の左上隅にあるトグル Screencast アイコンを使用して screencasting を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-156">When remote debugging an [Android device][DevToolsRemoteDebugAndroid], a [Windows 10 device][DevToolsRemoteDebugWindows], or a [Surface Duo emulator][DevToolsRemoteDebugDuoEmulator], you are able to toggle screencasting with the ![Toggle Screencast][ImageScreencastingIcon] icon in the top-left corner of the DevTools.</span></span>  <span data-ttu-id="6bf42-157">Screencasting を有効にすると、DevTools ウィンドウからリモートデバイスの Microsoft Edge でタブ内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-157">With screencasting enabled, you are able to navigate the tab in Microsoft Edge on the remote device from the DevTools window.</span></span>  <span data-ttu-id="6bf42-158">Microsoft Edge 84 では、これらのナビゲーションボタンは、キーボードからアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-158">In Microsoft Edge 84, these navigation buttons are now also keyboard accessible.</span></span>  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="Screencasted URL バーから Shift + Tab キーを押すと、[更新] ボタンにフォーカスが表示される" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   <span data-ttu-id="6bf42-160">`Shift` + `Tab` Screencasted URL バーを押すと、[**更新**] ボタンにフォーカスが表示される</span><span class="sxs-lookup"><span data-stu-id="6bf42-160">Pressing `Shift`+`Tab` from the screencasted URL bar shows focus on the **Refresh** button</span></span>
:::image-end:::  

<span data-ttu-id="6bf42-161">Chromium の問題[#1081486][CR1081486]</span><span class="sxs-lookup"><span data-stu-id="6bf42-161">Chromium issue [#1081486][CR1081486]</span></span>  

### <span data-ttu-id="6bf42-162">ネットワークパネルの詳細ウィンドウにアクセスできるようになりました</span><span class="sxs-lookup"><span data-stu-id="6bf42-162">Network panel Details pane is now accessible</span></span>  

<span data-ttu-id="6bf42-163">Microsoft Edge 84 では、ネットワーク[ログ][DevToolsNetworkLog]内のリソースに対して [**ネットワーク**] パネルを開くと、[[詳細] ウィンドウ][DevToolsNetworkDetails]がフォーカスされます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-163">In Microsoft Edge 84, the [Details pane][DevToolsNetworkDetails] in the **Network** panel now takes focus when you open it for a resource in the [Network Log][DevToolsNetworkLog].</span></span>  <span data-ttu-id="6bf42-164">この変更により、スクリーンリーダーは**詳細**ウィンドウの内容を読み上げて操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6bf42-164">This change allows screen readers to read out and interact with the content of the **Details** pane.</span></span>  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="[ネットワーク] パネルの詳細ウィンドウでは、開いたときにフォーカスが移動します。" lightbox="../../media/2020/05/network-details.msft.png":::
   <span data-ttu-id="6bf42-166">[**ネットワーク**] パネルの**詳細**ウィンドウでは、開いたときにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-166">The **Details** pane in the **Network** panel takes focus when opened</span></span>
:::image-end:::  

<span data-ttu-id="6bf42-167">Chromium の問題[#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="6bf42-167">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="6bf42-168">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="6bf42-168">Announcements from the Chromium project</span></span>  

<span data-ttu-id="6bf42-169">次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 84 で利用可能なその他の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-169">The following sections announce additional features available in Microsoft Edge 84 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="6bf42-170">DevTools のドローワの新しい問題ツールでサイトの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="6bf42-170">Fix site issues with the new Issues tool in the DevTools Drawer</span></span>

<span data-ttu-id="6bf42-171">DevTools のドロアーの新しい**問題**ツールは、**本体**の通知の疲労と低優先メールを削減するために構築されました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-171">The new **Issues** tool in the DevTools Drawer was built to help reduce the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="6bf42-172">現時点では、**コンソール**は、web サイトの開発者、ライブラリ、フレームワーク、Microsoft Edge がメッセージ、警告、エラーをログに記録するための中心的な場所です。</span><span class="sxs-lookup"><span data-stu-id="6bf42-172">Currently, the **Console** is the central place for website developers, libraries, frameworks, and Microsoft Edge to log messages, warnings, and errors.</span></span>  <span data-ttu-id="6bf42-173">**懸案事項**ツールは、ブラウザーからの警告を、構造化された、集計された実用的な方法で収集します。 Microsoft Edge devtools 内の影響を受けるリソースへのリンク、問題の修正方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-173">The **Issues** tool aggregates warnings from the browser in a structured, aggregated, and actionable way, links to affected resources within Microsoft Edge DevTools, and provides guidance on how to fix the issues.</span></span>  <span data-ttu-id="6bf42-174">時間の経過と共に、Microsoft Edge のツールでは **、本体で**はなく、[**問題**のツール] で、より多くの警告が表示されます。これにより、**本体**の低優先メール数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-174">Over time, you should see more and more warnings in Microsoft Edge surfacing in the **Issues** tool rather than the **Console**, which should help reduce the clutter in the **Console**.</span></span>  

<span data-ttu-id="6bf42-175">始めるには、「 [Microsoft Edge DevTools の問題を見つけて解決][DevtoolsIssuesIndex]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-175">To get started, see [Find And Fix Problems With The Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools のドローワの問題ツール" lightbox="../../media/2020/05/issues.msft.png":::
   <span data-ttu-id="6bf42-177">DevTools のドローワの**問題**ツール</span><span class="sxs-lookup"><span data-stu-id="6bf42-177">The **Issues** tool in the DevTools Drawer</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-178">Chromium の問題[#1068116][CR1068116]</span><span class="sxs-lookup"><span data-stu-id="6bf42-178">Chromium issue [#1068116][CR1068116]</span></span>  

### <span data-ttu-id="6bf42-179">検査モードのヒントでアクセシビリティ情報を表示する</span><span class="sxs-lookup"><span data-stu-id="6bf42-179">View accessibility information in the Inspect Mode tooltip</span></span>  

<span data-ttu-id="6bf42-180">**検査モード**のヒントは、要素にアクセシビリティ対応の[名前とロール][WebhintHintsAxeNameRoleValue]があり、[キーボードフォーカス][WebhintHintsAxeKeyboard]可能であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-180">The **Inspect Mode** tooltip now indicates whether the element has an accessible [name and role][WebhintHintsAxeNameRoleValue] and is [keyboard-focusable][WebhintHintsAxeKeyboard].</span></span>  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="アクセシビリティ情報が含まれる検査モードのヒント" lightbox="../../media/2020/05/a11y.msft.png":::
  <span data-ttu-id="6bf42-182">アクセシビリティ情報が含まれる**検査モード**のヒント</span><span class="sxs-lookup"><span data-stu-id="6bf42-182">The **Inspect Mode** tooltip with accessibility information</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-183">Chromium の問題[#1040025][CR1040025]</span><span class="sxs-lookup"><span data-stu-id="6bf42-183">Chromium issue [#1040025][CR1040025]</span></span>  

### <span data-ttu-id="6bf42-184">パフォーマンスパネルの更新</span><span class="sxs-lookup"><span data-stu-id="6bf42-184">Performance panel updates</span></span>  

#### <span data-ttu-id="6bf42-185">フッターのブロック時間情報の合計を表示する</span><span class="sxs-lookup"><span data-stu-id="6bf42-185">View Total Blocking Time information in the footer</span></span>  

<span data-ttu-id="6bf42-186">ロードパフォーマンスの記録後、[**パフォーマンス**] パネルには、フッター内のブロック時間 (tbt) 情報が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-186">After recording your load performance, the **Performance** panel now shows Total Blocking Time \(TBT\) information in the footer.</span></span>  <span data-ttu-id="6bf42-187">TBT は、ページが使用可能になるまでにかかる時間を数値化するのに役立つロードパフォーマンスメトリックです。</span><span class="sxs-lookup"><span data-stu-id="6bf42-187">TBT is a load performance metric that helps quantify how long a page takes to become usable.</span></span>  <span data-ttu-id="6bf42-188">基本的には、ページが使用可能になるまでの時間を測定します (コンテンツが画面にレンダリングされるためです)。ただし、JavaScript がメインスレッドをブロックしているため、実際には使用できません。そのため、ページはユーザー入力に応答しません。</span><span class="sxs-lookup"><span data-stu-id="6bf42-188">It essentially measures how long a page appears to be usable \(because the content is rendered to the screen\); but is not actually usable, because JavaScript is blocking the main thread and therefore the page does not respond to user input.</span></span>  <span data-ttu-id="6bf42-189">TBT は、おおよその最初の入力遅延の主な基準となります。</span><span class="sxs-lookup"><span data-stu-id="6bf42-189">TBT is the main metric for approximating First Input Delay.</span></span>  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

<span data-ttu-id="6bf42-190">ブロックの合計時間情報を取得するには、 **Refresh Page**ページの ![ ][ImageRefreshPageIcon] 読み込みのパフォーマンスを記録するために、ページの更新ページの更新アイコンのワークフローを使わないでください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-190">To get Total Blocking Time information, do not use the **Refresh Page** ![Refresh page icon][ImageRefreshPageIcon] workflow for recording page load performance.</span></span>  

<span data-ttu-id="6bf42-191">代わりに、[レコードレコード] アイコン**を選択し**、ページを手動で読み込むか ![ ][ImageRecordIcon] 、ページが読み込まれるのを待ってから、記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-191">Instead, select **Record** ![Record icon][ImageRecordIcon], manually reload the page, wait for the page to load, and then stop recording.</span></span>  

<span data-ttu-id="6bf42-192">`Total Blocking Time: Unavailable`Microsoft Edge DevTools では、Microsoft edge の内部プロファイリングデータから必要な情報を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6bf42-192">If you see `Total Blocking Time: Unavailable`, Microsoft Edge DevTools did not get the required information from the internal profiling data in Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="パフォーマンスパネル記録のフッターのブロック時間情報の合計" lightbox="../../media/2020/05/tbt.msft.png":::
   <span data-ttu-id="6bf42-194">**パフォーマンス**パネル記録のフッターのブロック時間情報の合計</span><span class="sxs-lookup"><span data-stu-id="6bf42-194">Total Blocking Time information in the footer of a **Performance** panel recording</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-195">Chromium の問題[#1054381][CR1054381]</span><span class="sxs-lookup"><span data-stu-id="6bf42-195">Chromium issue [#1054381][CR1054381]</span></span>  

#### <span data-ttu-id="6bf42-196">[新しいエクスペリエンス] セクションのレイアウトシフトのイベント</span><span class="sxs-lookup"><span data-stu-id="6bf42-196">Layout Shift events in the new Experience section</span></span>  

<span data-ttu-id="6bf42-197">[**パフォーマンス**] パネルの [新しい**エクスペリエンス**] セクションでは、レイアウトシフトを検出できます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-197">The new **Experience** section of the **Performance** panel helps you detect layout shifts.</span></span>  <span data-ttu-id="6bf42-198">累積レイアウトシフト \ (CLS \) は、表示が不安定になるのを防ぐためのメトリックです。</span><span class="sxs-lookup"><span data-stu-id="6bf42-198">Cumulative Layout Shift \(CLS\) is a metric that helps you quantify unwanted visual instability.</span></span>

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

<span data-ttu-id="6bf42-199">[**レイアウトシフト**] イベントを選択して、[**概要**] ウィンドウのレイアウトシフトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-199">Select the **Layout Shift** event to see the details of the layout shift in the **Summary** pane.</span></span>  <span data-ttu-id="6bf42-200">**移動**先と**移動**先のフィールドの上にマウスポインターを移動すると、レイアウトのシフトが発生した場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-200">Hover over the **Moved from** and **Moved to** fields to visualize where the layout shift occurred.</span></span>  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="レイアウトシフトの詳細" lightbox="../../media/2020/05/cls.msft.png":::
   <span data-ttu-id="6bf42-202">レイアウトシフトの詳細</span><span class="sxs-lookup"><span data-stu-id="6bf42-202">The details of a layout shift</span></span>  
:::image-end:::  

### <span data-ttu-id="6bf42-203">本体のより正確な promise 用語</span><span class="sxs-lookup"><span data-stu-id="6bf42-203">More accurate promise terminology in the Console</span></span>  

<span data-ttu-id="6bf42-204">ログインしたときに、 `Promise` **コンソール**の値が正しく指定されて `PromiseStatus` `resolved` いません。</span><span class="sxs-lookup"><span data-stu-id="6bf42-204">When logging a `Promise`, the **Console** incorrectly provided `PromiseStatus` value set to `resolved`.</span></span>  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="以前の解決された用語を使用した本体の例" lightbox="../../media/2020/05/resolved.msft.png":::
   <span data-ttu-id="6bf42-206">古い用語を使用した**本体**の例 `resolved`</span><span class="sxs-lookup"><span data-stu-id="6bf42-206">An example of the **Console** using the old `resolved` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-207">これで、**本体**で指定された用語が使用されるようになりました `fulfilled` `Promise` 。</span><span class="sxs-lookup"><span data-stu-id="6bf42-207">The **Console** now uses the term `fulfilled`, which aligns with the `Promise` specification.</span></span>  <span data-ttu-id="6bf42-208">仕様の詳細につい `Promise` ては、「 [GitHub の状態と Fates](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-208">For more information about the `Promise` specification, see [States and Fates on GitHub](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md).</span></span>  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="新しいフルフィルメント用語を使用した本体の例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  <span data-ttu-id="6bf42-210">新しい用語を使用した**本体**の例 `fulfilled`</span><span class="sxs-lookup"><span data-stu-id="6bf42-210">An example of the **Console** using the new `fulfilled` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-211">V8 の問題[#6751][CRV86751]</span><span class="sxs-lookup"><span data-stu-id="6bf42-211">V8 issue [#6751][CRV86751]</span></span>  

### <span data-ttu-id="6bf42-212">スタイルウィンドウの更新</span><span class="sxs-lookup"><span data-stu-id="6bf42-212">Styles pane updates</span></span>  

#### <span data-ttu-id="6bf42-213">Revert キーワードのサポート</span><span class="sxs-lookup"><span data-stu-id="6bf42-213">Support for the revert keyword</span></span>  

<span data-ttu-id="6bf42-214">[**スタイル**] ウィンドウのオートコンプリート UI で、[CSS の[元に戻す][MDNRevert]] キーワードが検出されるようになりました。これにより、プロパティのカスケード値が、要素のスタイル設定に適用された前の値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="6bf42-214">The autocomplete UI of the **Styles** pane now detects the [revert][MDNRevert] CSS keyword, which reverts the cascaded value of a property to the previous value applied to the styling of the element.</span></span>  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="元に戻すプロパティの値を設定する" lightbox="../../media/2020/05/revert.msft.png":::
  <span data-ttu-id="6bf42-216">元に戻すプロパティの値を設定する</span><span class="sxs-lookup"><span data-stu-id="6bf42-216">Setting the value of a property to revert</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-217">Chromium の問題[#1075437][CR1075437]</span><span class="sxs-lookup"><span data-stu-id="6bf42-217">Chromium issue [#1075437][CR1075437]</span></span>  

#### <span data-ttu-id="6bf42-218">イメージのプレビュー</span><span class="sxs-lookup"><span data-stu-id="6bf42-218">Image previews</span></span>  

<span data-ttu-id="6bf42-219">[スタイル] ウィンドウの値の上にマウスポインターを置くと、 `background-image` ヒントに画像のプレビューが表示されます。 **Styles**</span><span class="sxs-lookup"><span data-stu-id="6bf42-219">Hover over a `background-image` value in the **Styles** pane to see a preview of the image in a tooltip.</span></span>  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="背景画像の値の上にマウスポインターを置く" lightbox="../../media/2020/05/image-preview.msft.png":::
  <span data-ttu-id="6bf42-221">値の上にマウスポインターを置く `background-image`</span><span class="sxs-lookup"><span data-stu-id="6bf42-221">Hovering over a `background-image` value</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-222">Chromium の問題[#1040019][CR1040019]</span><span class="sxs-lookup"><span data-stu-id="6bf42-222">Chromium issue [#1040019][CR1040019]</span></span>  

#### <span data-ttu-id="6bf42-223">カラーピッカーでスペースで区切られた機能カラー表記が使用されるようになりました</span><span class="sxs-lookup"><span data-stu-id="6bf42-223">Color Picker now uses space-separated functional color notation</span></span>  

<span data-ttu-id="6bf42-224">[CSS カラーモジュールレベル 4][CSSWGDraftsColor4Changes3]では、などのカラー関数でスペース区切り引数をサポートすることを指定し `rgb()` ます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-224">[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] specifies that color functions, such as `rgb()`, should support space-separated arguments.</span></span>  <span data-ttu-id="6bf42-225">たとえば、`rgb(0, 0, 0)` は `rbg(0 0 0)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="6bf42-225">For example, `rgb(0, 0, 0)` is equivalent to `rbg(0 0 0)`.</span></span>  

<span data-ttu-id="6bf42-226">[**スタイル**] ウィンドウで、値を保持して選択することにより、[カラーピッカー][DevtoolsCssReferenceColorPicker]で色を選ぶか、色表現の代わりに色を選ぶと `Shift` `background-color` 、スペース区切りの引数構文が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-226">When you choose colors with the [Color Picker][DevtoolsCssReferenceColorPicker] or alternate between color representations in the **Styles** pane by holding `Shift` and selecting the `background-color` value, you should see the space-separated argument syntax.</span></span>  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="[スタイル] ウィンドウでスペースで区切られた引数を使用する" lightbox="../../media/2020/05/color.msft.png":::
  <span data-ttu-id="6bf42-228">[**スタイル**] ウィンドウでスペースで区切られた引数を使用する</span><span class="sxs-lookup"><span data-stu-id="6bf42-228">Using space-separated arguments in the **Styles** pane</span></span>  
:::image-end:::  

<span data-ttu-id="6bf42-229">また、**計算**されるウィンドウと**検査モード**のヒントで構文を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bf42-229">You should also see the syntax in the **Computed** pane and the **Inspect Mode** tooltip.</span></span>  

<span data-ttu-id="6bf42-230">Microsoft Edge DevTools では、新しい構文が使用されています。これは、 [color ()][CSSWGDraftsColor4Property]などの CSS 機能では、非推奨のコンマ区切り引数構文がサポートされていないためです。</span><span class="sxs-lookup"><span data-stu-id="6bf42-230">Microsoft Edge DevTools is using the new syntax because upcoming CSS features such as [color()][CSSWGDraftsColor4Property] do not support the deprecated comma-separated argument syntax.</span></span>  

<span data-ttu-id="6bf42-231">スペース区切りの引数構文は、ほとんどのブラウザーでしばらくサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6bf42-231">The space-separated argument syntax has been supported in most browsers for a while.</span></span>  <span data-ttu-id="6bf42-232">詳細については、「[スペースで区切られた機能カラー表記][CaniuseMDNSpaceSeparatedFunctionalColorNotations]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-232">For more information, see [Can I use: Space-separated functional color notations?][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span></span>  

<span data-ttu-id="6bf42-233">Chromium の問題[#1072952][CR1072952]</span><span class="sxs-lookup"><span data-stu-id="6bf42-233">Chromium issue [#1072952][CR1072952]</span></span>  

### <span data-ttu-id="6bf42-234">[要素] パネルの [プロパティ] ウィンドウの廃止</span><span class="sxs-lookup"><span data-stu-id="6bf42-234">Deprecation of the Properties pane in the Elements panel</span></span>  

<span data-ttu-id="6bf42-235">[**要素**] パネルの [**プロパティ**] ウィンドウは使われなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6bf42-235">The **Properties** pane in the **Elements** panel is deprecated.</span></span>  <span data-ttu-id="6bf42-236">`console.dir($0)`代わりに**本体**で実行します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-236">Run `console.dir($0)` in the **Console** instead.</span></span>  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="廃止されたプロパティのウィンドウ" lightbox="../../media/2020/05/properties.msft.png":::
   <span data-ttu-id="6bf42-238">廃止された**プロパティ**のウィンドウ</span><span class="sxs-lookup"><span data-stu-id="6bf42-238">The deprecated **Properties** pane</span></span>  
:::image-end:::  

#### <span data-ttu-id="6bf42-239">参考文献</span><span class="sxs-lookup"><span data-stu-id="6bf42-239">References</span></span>  

*   [<span data-ttu-id="6bf42-240">console. dir ()</span><span class="sxs-lookup"><span data-stu-id="6bf42-240">console.dir()</span></span>][DevtoolsConsoleApiDir]  
*   [<span data-ttu-id="6bf42-241">$0</span><span class="sxs-lookup"><span data-stu-id="6bf42-241">$0</span></span>][DevtoolsConsoleUtilitiesDom]  

### <span data-ttu-id="6bf42-242">[マニフェスト] ウィンドウでのアプリのショートカットのサポート</span><span class="sxs-lookup"><span data-stu-id="6bf42-242">App shortcuts support in the Manifest pane</span></span>  

<span data-ttu-id="6bf42-243">アプリのショートカットを使用すると、web アプリ内で一般的または推奨されるタスクをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-243">App shortcuts help users quickly start common or recommended tasks within a web app.</span></span>  <span data-ttu-id="6bf42-244">アプリのショートカットメニューは、ユーザーのデスクトップまたはモバイルデバイスにインストールされている[プログレッシブ Web アプリ][PwaIndex]についてのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-244">The app shortcuts menu is shown only for [Progressive Web Apps][PwaIndex] that are installed on the user's desktop or mobile device.</span></span>  

<!--For more information, see [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="[マニフェスト] ウィンドウのアプリのショートカット" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  <span data-ttu-id="6bf42-246">[**マニフェスト**] ウィンドウのアプリのショートカット</span><span class="sxs-lookup"><span data-stu-id="6bf42-246">App shortcuts in the **Manifest** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="6bf42-247">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="6bf42-247">Download the Microsoft Edge preview channels</span></span>   

<span data-ttu-id="6bf42-248">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels]を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6bf42-248">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="6bf42-249">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-249">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="6bf42-250">Microsoft Edge Devtools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="6bf42-250">Getting in touch with Microsoft Edge Devtools team</span></span>  

  

<span data-ttu-id="6bf42-251">投稿の新機能や変更点について、または DevTools に関連するその他のものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-251">To discuss the new features and changes in the post, or anything else related to DevTools:</span></span>  

*   <span data-ttu-id="6bf42-252">DevTools の**フィードバック**アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="6bf42-252">Send your feedback using the **Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="6bf42-253">[@EdgeDevTools][PostTweetEdgeDevTools]ツイート</span><span class="sxs-lookup"><span data-stu-id="6bf42-253">Tweet at [@EdgeDevTools][PostTweetEdgeDevTools]</span></span>  
*   <span data-ttu-id="6bf42-254">[目的の Web サイト][TheWebWeWant]に提案を送信する</span><span class="sxs-lookup"><span data-stu-id="6bf42-254">Submit a suggestion to [The Web We Want][TheWebWeWant]</span></span>  
*   <span data-ttu-id="6bf42-255">[エッジ開発者][GitHubMicrosoftDocsEdgeDeveloperNewIssue]リポジトリでこのページのファイルのバグを修正します。</span><span class="sxs-lookup"><span data-stu-id="6bf42-255">File bugs on this page in the [edge-developer][GitHubMicrosoftDocsEdgeDeveloperNewIssue] repository</span></span>  

:::image type="complex" source="../../media/2020/05/feedback-icon.msft.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン" lightbox="../../media/2020/05/feedback-icon.msft.png":::
  <span data-ttu-id="6bf42-257">Microsoft Edge DevTools の**フィードバック**アイコン</span><span class="sxs-lookup"><span data-stu-id="6bf42-257">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools の設定アイコン"
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/images/toggle-screencast-icon.msft.png "DevTools トグル Screencasting アイコン"
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png "DevTools のパフォーマンスパネルのページの更新アイコン"
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png "DevTools のパフォーマンスパネルのレコードアイコン"

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用する |Microsoft ドキュメント"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir-本体 API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選んだ要素または JavaScript オブジェクト-コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "カラーピッカーで色を変更する-CSS リファレンス |Microsoft ドキュメント"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "引き出し-概要のカスタマイズ |Microsoft ドキュメント"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の [問題] タブの問題を見つけて解決する |Microsoft ドキュメント"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Android デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "リモートデバッグ Surface Duo エミュレーターの概要 |Microsoft ドキュメント"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "リソースの詳細を調べる |Microsoft ドキュメント"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワークアクティビティのログ |Microsoft ドキュメント"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ |Microsoft ドキュメント"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android アプリ"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "スペースで区切られた機能カラーの表記法-MDN |使用できますか"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"

[CR174309]: https://crbug.com/174309 "DevTools: キーボードショートカット/キーバインディングのカスタマイズを許可する |Chromium のバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG に準拠していません |Chromium のバグ"  
[CR1040019]: https://crbug.com/1040019 "DevTools: [スタイル] ウィンドウで画像や背景画像を簡単にプレビューできます。Chromium のバグ"  
[CR1040025]: https://crbug.com/1040025 "DevTools: 要素 popover での基本的な a11y 情報の表示 |Chromium のバグ"  
[CR1048378]: https://crbug.com/1048378 "DevTools UI のハイコントラストモードのサポート |Chromium のバグ"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium のバグ"  
[CR1068116]: https://crbug.com/1068116 "出荷問題パネル |Chromium のバグ"  
[CR1072952]: https://crbug.com/1072952 "DevTools: color picker は、モダン CSS の色の構文を生成する必要があります。Chromium のバグ"  
[CR1075437]: https://crbug.com/1075437 "DevTools: CSS ' revert ' キーワード/値のサポートを追加します。Chromium のバグ"  
[CR1076112]: https://crbug.com/1076112 "Devtools の個人用設定-引き出しのポインター"  
[CR1081486]: https://crbug.com/1081486 "キーボードフォーカスは、screencast モードのナビゲーションボタンには表示されません。Chromium のバグ"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus は「フルフィルメント」であり、「解決済み」ではないV8 のバグ"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "色の変更 3-CSS の色モジュールレベル 4 |W3C CSS ワーキンググループエディターの下書き"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. フォアグラウンド色: ' color '-CSS カラーモジュールレベル 4 |W3C CSS ワーキンググループエディターの下書き"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新しい Microsoft Edge の紹介"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "州と Fates-domenic/promise-ラップする |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "元に戻す |MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "ブラウザーの互換性 |MDN"  

[VSCode]: https://code.visualstudio.com/ "Visual Studio コード"  
[VSCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Windows 用 Visual Studio コードのキーボードショートカット"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "アックス: キーボード |Web ヒント"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "アックス: Name Role 値 |Web ヒント"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "Windows でハイコントラストモードをオンまたはオフにする |Windows のサポート"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"  

<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebdevCoreWebVitals]: https://alphabet-dev/vitals#core-web-vitals "Core Web Vitals | alphabet-dev"  -->  

> [!NOTE]
> <span data-ttu-id="6bf42-306">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6bf42-306">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6bf42-307">元のページは[ここ](https://developers.google.com/web/updates/2020/05/devtools/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="6bf42-307">The original page is found [here](https://developers.google.com/web/updates/2020/05/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6bf42-309">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6bf42-309">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
