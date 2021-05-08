---
description: ハイ コントラスト モードで DevTools をWindows、DevTools のキーボード ショートカットを一致Visual Studio Codeなどです。
title: DevTools の新機能 (Microsoft Edge 84)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 01d41fe5400dde427a0ac73870ace0e1211f429a
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514390"
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
# <a name="whats-new-in-devtools-microsoft-edge-84"></a><span data-ttu-id="1334a-104">DevTools の新機能 (Microsoft Edge 84)</span><span class="sxs-lookup"><span data-stu-id="1334a-104">What's new in DevTools (Microsoft Edge 84)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1334a-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="1334a-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="1334a-106">以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1334a-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="1334a-107">DevTools、コード拡張機能、その他の新機能を試Microsoft Visual Studioお知らせをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1334a-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="1334a-108">開発者ツールのすべての最新および最大の機能を最新の情報に更新するには、プレビュー チャネルMicrosoft Edge[][MicrosoftEdgePreviewChannels]ダウンロードし[、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。</span><span class="sxs-lookup"><span data-stu-id="1334a-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="use-the-devtools-in-windows-high-contrast-mode"></a><span data-ttu-id="1334a-109">ハイ コントラスト モードで DevTools をWindowsする</span><span class="sxs-lookup"><span data-stu-id="1334a-109">Use the DevTools in Windows high contrast mode</span></span>

<span data-ttu-id="1334a-110">このMicrosoft Edge DevTools がハイ コントラスト モードの場合、Windowsハイ コントラスト モードで表示されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-110">The Microsoft Edge DevTools are now displayed in high contrast mode when Windows is in high contrast mode.</span></span>  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="ハイ コントラスト Microsoft Edge DevTools の機能" lightbox="../../media/2020/05/high-contrast.msft.png":::
   <span data-ttu-id="1334a-112">ハイ コントラスト Microsoft Edge DevTools の機能</span><span class="sxs-lookup"><span data-stu-id="1334a-112">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-113">[手順に従って、ハイ コントラスト][MicrosoftSupportWindows10HighContrastMode]モードをオンWindows。</span><span class="sxs-lookup"><span data-stu-id="1334a-113">[Follow the instructions to turn on high contrast mode in Windows][MicrosoftSupportWindows10HighContrastMode].</span></span>  <span data-ttu-id="1334a-114">アプリケーションで DevTools を開Microsoft Edgeまたはを `F12` 選択します `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="1334a-114">To open the DevTools in Microsoft Edge, select `F12` or `Ctrl`+`Shift`+`I`.</span></span>  <span data-ttu-id="1334a-115">DevTools はハイ コントラスト モードで表示されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-115">The DevTools are displayed in high contrast mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="1334a-116">DevTools Microsoft Edgeは現在、macOS 上ではなく、Windowsハイ コントラスト モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1334a-116">The Microsoft Edge DevTools currently support high contrast mode on Windows but not on macOS.</span></span>  

<span data-ttu-id="1334a-117">Chromium[問題#1048378][CR1048378]</span><span class="sxs-lookup"><span data-stu-id="1334a-117">Chromium issue [#1048378][CR1048378]</span></span>  

### <a name="match-keyboard-shortcuts-in-the-devtools-to-visual-studio-code"></a><span data-ttu-id="1334a-118">DevTools のキーボード ショートカットを Visual Studio Code と一致させる</span><span class="sxs-lookup"><span data-stu-id="1334a-118">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  

<span data-ttu-id="1334a-119">フィードバックと[パブリック](#getting-in-touch-with-microsoft-edge-devtools-team)Chromiumトラッカー[][CRIssuesList]から、Microsoft Edge DevTools チームは、DevTools でキーボード ショートカットをカスタマイズする機能が必要なことを学習しました。</span><span class="sxs-lookup"><span data-stu-id="1334a-119">From your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) and the [Chromium public issue tracker][CRIssuesList], the Microsoft Edge DevTools team learned that you wanted the ability to customize keyboard shortcuts in the DevTools.</span></span>  <span data-ttu-id="1334a-120">このMicrosoft Edge 84 では[、DevTools][VisualStudioCode]のキーボード ショートカットを Visual Studio Code に一致できます。これは、チームがショートカットのカスタマイズに取り組む機能の 1 つにすすむ機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="1334a-120">In Microsoft Edge 84, you are now able to match keyboard shortcuts in the DevTools to [Visual Studio Code][VisualStudioCode], which is just one of the features the team is working on for shortcut customization.</span></span>  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="DevTools のキーボード ショートカットを Visual Studio Code と一致させる" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   <span data-ttu-id="1334a-122">ハイ コントラスト Microsoft Edge DevTools の機能</span><span class="sxs-lookup"><span data-stu-id="1334a-122">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-123">実験を試す場合は、DevTools 設定 の右上隅にある DevTools 設定 アイコンアイコンを選択または選択して `?` ![ 、DevTools 設定 を開 ][ImageSettingsIcon] きます。</span><span class="sxs-lookup"><span data-stu-id="1334a-123">To try the experiment, open DevTools Settings by selecting `?` or choosing the ![DevTools Settings icon][ImageSettingsIcon] icon in the top-right corner of the DevTools.</span></span>  <span data-ttu-id="1334a-124">[実験] セクション **に移動し、[** カスタム キーボード ショートカット設定を有効にする] タブ (再読み込 **みが必要) をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="1334a-124">Navigate to the **Experiments** section and check **Enable custom keyboard shortcuts settings tab (requires reload)**.</span></span>  <span data-ttu-id="1334a-125">DevTools を再読み込みし、設定開き、[ショートカット]**セクションに移動**します。</span><span class="sxs-lookup"><span data-stu-id="1334a-125">Now reload the DevTools, open Settings again, and navigate to the **Shortcuts** section.</span></span>  

<span data-ttu-id="1334a-126">[**プリセットからショートカットを一致する] ドロップダウンで [DevTools( Default)** ] を選択し、[既定] Visual Studio Code を**選択します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1334a-126">Choose **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="1334a-127">DevTools のキーボード ショートカットが、同じ操作のショートカットと一致Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="1334a-127">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in Visual Studio Code.</span></span>  

<span data-ttu-id="1334a-128">たとえば、[Visual Studio Code][VisualStudioCodeShortcuts] でスクリプトを一時停止または実行し続けるためのキーボード ショートカットは `F5` です。</span><span class="sxs-lookup"><span data-stu-id="1334a-128">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualStudioCodeShortcuts] is `F5`.</span></span>  <span data-ttu-id="1334a-129">**DevTools (Default)** プリセットを使用すると、DevTools の同じショートカットが、Visual Studio Codeプリセットと同じショートカットになります。 `F8` \*\*\*\* `F5`</span><span class="sxs-lookup"><span data-stu-id="1334a-129">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8` but with the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="1334a-130">この機能は現在、Microsoft Edge 84 で使用できますので、チームとフィードバック[を](#getting-in-touch-with-microsoft-edge-devtools-team)共有してください。</span><span class="sxs-lookup"><span data-stu-id="1334a-130">The feature is currently available in Microsoft Edge 84 as an experiment, so please share your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) with the team!</span></span>  

<span data-ttu-id="1334a-131">Chromium の問題 [#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="1334a-131">Chromium issue [#174309][CR174309]</span></span>  

### <a name="remote-debug-surface-duo-emulators"></a><span data-ttu-id="1334a-132">リモート デバッグ Surface Duo エミュレーター</span><span class="sxs-lookup"><span data-stu-id="1334a-132">Remote debug Surface Duo emulators</span></span>  

<span data-ttu-id="1334a-133">これで、Surface Duo エミュレーターで実行されている Web コンテンツを[、DevTools][DualScreensAndroidEmulator]のフル パワーを使用してリモート[でデバッグMicrosoft Edgeできます][DevToolsChromiumGuide]。</span><span class="sxs-lookup"><span data-stu-id="1334a-133">You are now able to remotely debug your web content running in the [Surface Duo emulator][DualScreensAndroidEmulator] using the full power of the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

<span data-ttu-id="1334a-134">Surface [Duo エミュレーターを使用][DualScreensAndroidEmulator]すると、折りたたみ可能なデュアルスクリーン デバイスの新しいクラスで Web コンテンツがどのようにレンダリングされるのかテストできます。</span><span class="sxs-lookup"><span data-stu-id="1334a-134">With the [Surface Duo emulator][DualScreensAndroidEmulator], you are able to test how your web content renders on a new class of foldable and dual-screen devices.</span></span>  <span data-ttu-id="1334a-135">エミュレーターは Android オペレーティング システムを実行し、Android アプリMicrosoft Edge[提供します][AndroidEdge]。</span><span class="sxs-lookup"><span data-stu-id="1334a-135">The emulator runs the Android operating system and provides the [Microsoft Edge Android app][AndroidEdge].</span></span>  <span data-ttu-id="1334a-136">Web コンテンツをアプリに読みMicrosoft Edge [DevTools][DevToolsChromiumGuide]でデバッグMicrosoft Edgeします。 [][AndroidEdge]</span><span class="sxs-lookup"><span data-stu-id="1334a-136">Load your web content in the [Microsoft Edge app][AndroidEdge] and debug it with the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="Surface Duo Microsoft Edgeで実行されているアプリの一部" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   <span data-ttu-id="1334a-138">Surface Duo Microsoft Edgeのアプリ</span><span class="sxs-lookup"><span data-stu-id="1334a-138">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-139">Surface Duo エミュレーターで実行Microsoft Edge開いているタブまたは PWA の一覧を含む `edge://inspect` [][DesktopEdge]**SurfaceDuoEmulator**が表示されるデスクトップ インスタンス[][PwaIndex][の][DualScreensAndroidEmulator]ページです。</span><span class="sxs-lookup"><span data-stu-id="1334a-139">The `edge://inspect` page in a desktop instance of [Microsoft Edge][DesktopEdge] shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaIndex] that are running on the [Surface Duo emulator][DualScreensAndroidEmulator].</span></span>  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="[edge://inspect] ページには、エミュレーターで実行されているアプリMicrosoft Edgeタブの一覧が表示されます。" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   <span data-ttu-id="1334a-141">この `edge://inspect` ページには、エミュレーターで実行されているアプリMicrosoft Edgeタブの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-141">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>
:::image-end:::  

<span data-ttu-id="1334a-142">デバッグ**する**タブまたはデバッグするPWAを調Microsoft Edge[選択します][DevToolsChromiumGuide]。</span><span class="sxs-lookup"><span data-stu-id="1334a-142">Choose **inspect** for the tab or PWA that you want to debug to open the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  <span data-ttu-id="1334a-143">Surface Duo エミュレーターで Web コンテンツをリモートでデバッグするには、ステップ[バイ ステップ ガイドに従います][DevToolsRemoteDebugDuoEmulator]。</span><span class="sxs-lookup"><span data-stu-id="1334a-143">[Follow the step-by-step guide to remotely debug your web content on the Surface Duo emulator][DevToolsRemoteDebugDuoEmulator].</span></span>  

### <a name="resize-the-devtools-drawer-more-easily"></a><span data-ttu-id="1334a-144">DevTools ドロワーのサイズを簡単に変更する</span><span class="sxs-lookup"><span data-stu-id="1334a-144">Resize the DevTools drawer more easily</span></span>  

<span data-ttu-id="1334a-145">83 Microsoft Edge以前のバージョンでは、ドロワーのツールバー内をホバリングして[DevTools ドロ][DevToolsDrawer]ワーのサイズを変更するのみ可能でした。</span><span class="sxs-lookup"><span data-stu-id="1334a-145">In Microsoft Edge 83 or earlier, you were only able to resize the [DevTools Drawer][DevToolsDrawer] by hovering inside the toolbar of the Drawer.</span></span>  <span data-ttu-id="1334a-146">ドロワーの動作は、DevTools 内のペインの他のサイズ変更コントロールとは異なって動作し、ウィンドウの枠線にマウス ポインターを移動してサイズを変更しました。</span><span class="sxs-lookup"><span data-stu-id="1334a-146">The Drawer behaved differently than the other resize controls for panes in the DevTools where you hover on the border of the pane to resize it.</span></span>  <span data-ttu-id="1334a-147">次の画像を選択すると、ドロワーのサイズ変更がバージョン 83 以前のバージョンでどのように機能Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="1334a-147">Choose the following image to display how resizing the Drawer worked in version 83 or earlier of Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="DevTools ドロワーのサイズ変更 (Microsoft Edge 83)" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   <span data-ttu-id="1334a-149">DevTools ドロワーのサイズ変更 (Microsoft Edge 83)</span><span class="sxs-lookup"><span data-stu-id="1334a-149">Resizing the DevTools Drawer in Microsoft Edge 83</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="1334a-150">84 Microsoft Edgeから、ドロワーの枠線にカーソルを合わせて、ドロワーのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1334a-150">Starting with Microsoft Edge 84, you are now able to resize the Drawer by hovering over the border of the Drawer.</span></span>  <span data-ttu-id="1334a-151">この変更により、DevTools ドロワーのサイズを変更する動作と、DevTools 内の他のウィンドウのサイズを変更する方法が揃います。</span><span class="sxs-lookup"><span data-stu-id="1334a-151">This change aligns the behavior resizing the DevTools Drawer with the way you resize other panes in the DevTools.</span></span>  <span data-ttu-id="1334a-152">次の画像を選択して、84 のサイズ変更をMicrosoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="1334a-152">Choose the following image to display resizing in action in Microsoft Edge 84.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="DevTools ドロワーのサイズ変更 (Microsoft Edge 84)" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   <span data-ttu-id="1334a-154">DevTools ドロワーのサイズ変更 (Microsoft Edge 84)</span><span class="sxs-lookup"><span data-stu-id="1334a-154">Resizing the DevTools Drawer in Microsoft Edge 84</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="1334a-155">Chromium[問題#1076112][CR1076112]</span><span class="sxs-lookup"><span data-stu-id="1334a-155">Chromium issue [#1076112][CR1076112]</span></span>  

### <a name="screencasting-navigation-buttons-display-focus"></a><span data-ttu-id="1334a-156">スクリーン キャスト ナビゲーション ボタンにフォーカスが表示される</span><span class="sxs-lookup"><span data-stu-id="1334a-156">Screencasting navigation buttons display focus</span></span>  

<span data-ttu-id="1334a-157">[Android][DevToolsRemoteDebugAndroid]デバイス[、Windows 10][DevToolsRemoteDebugWindows]デバイス、[または Surface Duo][DevToolsRemoteDebugDuoEmulator]エミュレーターをリモート デバッグする場合は ![ 、DevTools の左上隅にある [画面キャストの切り替え] アイコンを使用してスクリーン キャストを切り替えられます。 ][ImageScreencastingIcon]</span><span class="sxs-lookup"><span data-stu-id="1334a-157">When remote debugging an [Android device][DevToolsRemoteDebugAndroid], a [Windows 10 device][DevToolsRemoteDebugWindows], or a [Surface Duo emulator][DevToolsRemoteDebugDuoEmulator], you are able to toggle screencasting with the ![Toggle Screencast][ImageScreencastingIcon] icon in the top-left corner of the DevTools.</span></span>  <span data-ttu-id="1334a-158">スクリーンキャストが有効になっている場合は、リモート デバイスMicrosoft Edge DevTools ウィンドウからタブを移動できます。</span><span class="sxs-lookup"><span data-stu-id="1334a-158">With screencasting enabled, you are able to navigate the tab in Microsoft Edge on the remote device from the DevTools window.</span></span>  <span data-ttu-id="1334a-159">84 Microsoft Edge、これらのナビゲーション ボタンはキーボードでもアクセス可能です。</span><span class="sxs-lookup"><span data-stu-id="1334a-159">In Microsoft Edge 84, these navigation buttons are now also keyboard accessible.</span></span>  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="スクリーン キャストされた URL バーから [Shift+ Tab] を選択すると、[更新] ボタンにフォーカスが表示されます" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   <span data-ttu-id="1334a-161">スクリーン `Shift` + `Tab` キャストされた URL バーから選択すると、[更新] ボタンにフォーカスが**表示**されます</span><span class="sxs-lookup"><span data-stu-id="1334a-161">Select `Shift`+`Tab` from the screencasted URL bar shows focus on the **Refresh** button</span></span>
:::image-end:::  

<span data-ttu-id="1334a-162">Chromium[問題#1081486][CR1081486]</span><span class="sxs-lookup"><span data-stu-id="1334a-162">Chromium issue [#1081486][CR1081486]</span></span>  

### <a name="network-panel-details-pane-is-now-accessible"></a><span data-ttu-id="1334a-163">ネットワーク パネルの [詳細] ウィンドウにアクセス可能</span><span class="sxs-lookup"><span data-stu-id="1334a-163">Network panel Details pane is now accessible</span></span>  

<span data-ttu-id="1334a-164">84 Microsoft Edgeでは、ネットワーク ログ[][DevToolsNetworkDetails]でリソースを開\*\*\*\* く際に、[ネットワーク] ツールの [詳細] ウィンドウにフォーカス[が集中します][DevToolsNetworkLog]。</span><span class="sxs-lookup"><span data-stu-id="1334a-164">In Microsoft Edge 84, the [Details pane][DevToolsNetworkDetails] in the **Network** tool now takes focus when you open it for a resource in the [Network Log][DevToolsNetworkLog].</span></span>  <span data-ttu-id="1334a-165">この変更により、スクリーン リーダーは詳細ウィンドウのコンテンツを読み取り、 **操作** できます。</span><span class="sxs-lookup"><span data-stu-id="1334a-165">This change allows screen readers to read out and interact with the content of the **Details** pane.</span></span>  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="[ネットワーク] パネルの [詳細] ウィンドウが開いたときにフォーカスを受け取る" lightbox="../../media/2020/05/network-details.msft.png":::
   <span data-ttu-id="1334a-167">ネットワーク **ツールの** [詳細] **ウィンドウが** 開いたときにフォーカスを受け取る</span><span class="sxs-lookup"><span data-stu-id="1334a-167">The **Details** pane in the **Network** tool takes focus when opened</span></span>
:::image-end:::  

<span data-ttu-id="1334a-168">Chromium[の問題][CR963183]#963183</span><span class="sxs-lookup"><span data-stu-id="1334a-168">Chromium issue [#963183][CR963183]</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="1334a-169">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="1334a-169">Announcements from the Chromium project</span></span>  

<span data-ttu-id="1334a-170">次のセクションでは、プロジェクトのオープン ソースにMicrosoft Edgeされた 84 で利用可能な追加のChromiumします。</span><span class="sxs-lookup"><span data-stu-id="1334a-170">The following sections announce additional features available in Microsoft Edge 84 that were contributed to the open source Chromium project.</span></span>  

### <a name="fix-site-issues-with-the-new-issues-tool-in-the-devtools-drawer"></a><span data-ttu-id="1334a-171">DevTools ドロワーの新しい Issues ツールでサイトの問題を修正する</span><span class="sxs-lookup"><span data-stu-id="1334a-171">Fix site issues with the new Issues tool in the DevTools Drawer</span></span>

<span data-ttu-id="1334a-172">**DevTools ドロワー**の新しい問題ツールは、コンソールの通知の疲労と混乱を軽減するために構築**されました**。</span><span class="sxs-lookup"><span data-stu-id="1334a-172">The new **Issues** tool in the DevTools Drawer was built to help reduce the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="1334a-173">現在、**コンソールは、Web**サイトの開発者、ライブラリ、フレームワーク、およびユーザーがメッセージ、警告、エラー Microsoft Edgeを記録する中心的な場所です。</span><span class="sxs-lookup"><span data-stu-id="1334a-173">Currently, the **Console** is the central place for website developers, libraries, frameworks, and Microsoft Edge to log messages, warnings, and errors.</span></span>  <span data-ttu-id="1334a-174">Issues ツールは、構造化された、集約された、操作可能な方法でブラウザーからの警告を集約し、Microsoft Edge DevTools 内の影響を受けるリソースへのリンク、および問題の修正方法に関するガイダンスを提供します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1334a-174">The **Issues** tool aggregates warnings from the browser in a structured, aggregated, and actionable way, links to affected resources within Microsoft Edge DevTools, and provides guidance on how to fix the issues.</span></span>  <span data-ttu-id="1334a-175">時間がたつ間に、コンソールではなく問題ツールの Microsoft Edge で多\*\*\*\* くの警告が表示され、コンソール\*\*\*\* の混乱を減らすのに役立**ちます**。</span><span class="sxs-lookup"><span data-stu-id="1334a-175">Over time, more and more warnings are surfaced in Microsoft Edge in the **Issues** tool rather than the **Console**, which should help reduce the clutter in the **Console**.</span></span>  

<span data-ttu-id="1334a-176">開始するには、[DevTools の問題の検索と修正] ツールMicrosoft Edge[に移動します][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="1334a-176">To get started, navigate to [Find And Fix Problems With The Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools ドロワーの問題ツール" lightbox="../../media/2020/05/issues.msft.png":::
   <span data-ttu-id="1334a-178">**DevTools**ドロワーの問題ツール</span><span class="sxs-lookup"><span data-stu-id="1334a-178">The **Issues** tool in the DevTools Drawer</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-179">Chromiumの問題[#1068116][CR1068116]</span><span class="sxs-lookup"><span data-stu-id="1334a-179">Chromium issue [#1068116][CR1068116]</span></span>  

### <a name="view-accessibility-information-in-the-inspect-mode-tooltip"></a><span data-ttu-id="1334a-180">[検査モード] ツールヒントでアクセシビリティ情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1334a-180">View accessibility information in the Inspect Mode tooltip</span></span>  

<span data-ttu-id="1334a-181">[**検査モード]** ツールヒントは、要素にアクセス可能な名前[][WebhintHintsAxeNameRoleValue]と役割を持ち、キーボードフォーカスが可能[かどうかを示します][WebhintHintsAxeKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="1334a-181">The **Inspect Mode** tooltip now indicates whether the element has an accessible [name and role][WebhintHintsAxeNameRoleValue] and is [keyboard-focusable][WebhintHintsAxeKeyboard].</span></span>  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="アクセシビリティ情報を含む検査モードのヒント" lightbox="../../media/2020/05/a11y.msft.png":::
  <span data-ttu-id="1334a-183">アクセシビリティ **情報を含** む検査モードのヒント</span><span class="sxs-lookup"><span data-stu-id="1334a-183">The **Inspect Mode** tooltip with accessibility information</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-184">Chromium[問題#1040025][CR1040025]</span><span class="sxs-lookup"><span data-stu-id="1334a-184">Chromium issue [#1040025][CR1040025]</span></span>  

### <a name="performance-panel-updates"></a><span data-ttu-id="1334a-185">[パフォーマンス] パネルの更新</span><span class="sxs-lookup"><span data-stu-id="1334a-185">Performance panel updates</span></span>  

#### <a name="view-total-blocking-time-information-in-the-footer"></a><span data-ttu-id="1334a-186">フッターにブロック時間の合計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1334a-186">View Total Blocking Time information in the footer</span></span>  

<span data-ttu-id="1334a-187">読み込みパフォーマンスを記録すると、[ **パフォーマンス** ] パネルにフッターに [合計ブロック時間] \(TBT\) 情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-187">After recording your load performance, the **Performance** panel now shows Total Blocking Time \(TBT\) information in the footer.</span></span>  <span data-ttu-id="1334a-188">TBT は読み込みパフォーマンスの指標で、ページが使用できる時間を数値化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1334a-188">TBT is a load performance metric that helps quantify how long a page takes to become usable.</span></span>  <span data-ttu-id="1334a-189">基本的には、ページが使用できる \(コンテンツが screen\にレンダリングされるので)使用できる時間を測定します。JavaScript がメイン スレッドをブロックするため、ページはユーザー入力に応答しないので、実際には使用できません。</span><span class="sxs-lookup"><span data-stu-id="1334a-189">It essentially measures how long a page appears to be usable \(because the content is rendered to the screen\); but is not actually usable, because JavaScript is blocking the main thread and therefore the page does not respond to user input.</span></span>  <span data-ttu-id="1334a-190">TBT は、最初の入力遅延を近似する主な指標です。</span><span class="sxs-lookup"><span data-stu-id="1334a-190">TBT is the main metric for approximating First Input Delay.</span></span>  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

<span data-ttu-id="1334a-191">[合計ブロック時間] 情報を取得するには、\*\*\*\* ページ読み込みパフォーマンスを記録するために [ページの更新] ページの更新アイコン ![ ][ImageRefreshPageIcon] ワークフローを使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="1334a-191">To get Total Blocking Time information, do not use the **Refresh Page** ![Refresh page icon][ImageRefreshPageIcon] workflow for recording page load performance.</span></span>  

<span data-ttu-id="1334a-192">代わりに、[ **レコード] アイコンを**選択し、ページを手動で再読み込みし、ページが読み込むのを待ち、記録 ![ ][ImageRecordIcon] を停止します。</span><span class="sxs-lookup"><span data-stu-id="1334a-192">Instead, select **Record** ![Record icon][ImageRecordIcon], manually reload the page, wait for the page to load, and then stop recording.</span></span>  

<span data-ttu-id="1334a-193">表示 `Total Blocking Time: Unavailable` されている場合はMicrosoft Edge DevTools で内部プロファイル データから必要な情報を取得Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="1334a-193">If `Total Blocking Time: Unavailable` is displayed, Microsoft Edge DevTools did not get the required information from the internal profiling data in Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="パフォーマンス パネルの記録のフッターの合計ブロック時間情報" lightbox="../../media/2020/05/tbt.msft.png":::
   <span data-ttu-id="1334a-195">パフォーマンス パネルの記録のフッターの合計 **ブロック時間** 情報</span><span class="sxs-lookup"><span data-stu-id="1334a-195">Total Blocking Time information in the footer of a **Performance** panel recording</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-196">Chromium[問題#1054381][CR1054381]</span><span class="sxs-lookup"><span data-stu-id="1334a-196">Chromium issue [#1054381][CR1054381]</span></span>  

#### <a name="layout-shift-events-in-the-new-experience-section"></a><span data-ttu-id="1334a-197">[新しいエクスペリエンス] セクションの [Shift イベントのレイアウト]</span><span class="sxs-lookup"><span data-stu-id="1334a-197">Layout Shift events in the new Experience section</span></span>  

<span data-ttu-id="1334a-198">[パフォーマンス **] パネルの** 新しい **[エクスペリエンス] セクション** を使用すると、レイアウトシフトを検出できます。</span><span class="sxs-lookup"><span data-stu-id="1334a-198">The new **Experience** section of the **Performance** panel helps you detect layout shifts.</span></span>  <span data-ttu-id="1334a-199">累積レイアウト シフト \(CLS\) は、望ましくない視覚不安定を定量化するのに役立つ指標です。</span><span class="sxs-lookup"><span data-stu-id="1334a-199">Cumulative Layout Shift \(CLS\) is a metric that helps you quantify unwanted visual instability.</span></span>

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

<span data-ttu-id="1334a-200">[レイアウト **シフト] イベントを** 選択して、[概要] ウィンドウにレイアウト シフトの詳細 **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="1334a-200">Choose the **Layout Shift** event to display the details of the layout shift in the **Summary** pane.</span></span>  <span data-ttu-id="1334a-201">[移動先 **] フィールドと [\*\*\*\*移動先**] フィールドにカーソルを合わせると、レイアウトシフトが発生した場所を視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="1334a-201">Hover on the **Moved from** and **Moved to** fields to visualize where the layout shift occurred.</span></span>  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="レイアウト シフトの詳細" lightbox="../../media/2020/05/cls.msft.png":::
   <span data-ttu-id="1334a-203">レイアウト シフトの詳細</span><span class="sxs-lookup"><span data-stu-id="1334a-203">The details of a layout shift</span></span>  
:::image-end:::  

### <a name="more-accurate-promise-terminology-in-the-console"></a><span data-ttu-id="1334a-204">コンソールのより正確な約束の用語</span><span class="sxs-lookup"><span data-stu-id="1334a-204">More accurate promise terminology in the Console</span></span>  

<span data-ttu-id="1334a-205">ログを記録すると `Promise` 、 **コンソールに正** しく指定されていない `PromiseStatus` 値がに設定されます `resolved` 。</span><span class="sxs-lookup"><span data-stu-id="1334a-205">When logging a `Promise`, the **Console** incorrectly provided `PromiseStatus` value set to `resolved`.</span></span>  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="古い解決済み用語を使用するコンソールの例" lightbox="../../media/2020/05/resolved.msft.png":::
   <span data-ttu-id="1334a-207">古い用語を **使用した** コンソールの `resolved` 例</span><span class="sxs-lookup"><span data-stu-id="1334a-207">An example of the **Console** using the old `resolved` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-208">コンソール **では** 、仕様に合 `fulfilled` わせて用語が使用 `Promise` されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-208">The **Console** now uses the term `fulfilled`, which aligns with the `Promise` specification.</span></span>  <span data-ttu-id="1334a-209">仕様の詳細については、「States `Promise` and [Fates on GitHub 」 に移動します](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)。</span><span class="sxs-lookup"><span data-stu-id="1334a-209">For more information about the `Promise` specification, navigate to [States and Fates on GitHub](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md).</span></span>  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="新しい満たされた用語を使用するコンソールの例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  <span data-ttu-id="1334a-211">新しい用語を **使用する** コンソールの `fulfilled` 例</span><span class="sxs-lookup"><span data-stu-id="1334a-211">An example of the **Console** using the new `fulfilled` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-212">V8 の [問題#6751][CRV86751]</span><span class="sxs-lookup"><span data-stu-id="1334a-212">V8 issue [#6751][CRV86751]</span></span>  

### <a name="styles-pane-updates"></a><span data-ttu-id="1334a-213">スタイル ウィンドウの更新</span><span class="sxs-lookup"><span data-stu-id="1334a-213">Styles pane updates</span></span>  

#### <a name="support-for-the-revert-keyword"></a><span data-ttu-id="1334a-214">revert キーワードのサポート</span><span class="sxs-lookup"><span data-stu-id="1334a-214">Support for the revert keyword</span></span>  

<span data-ttu-id="1334a-215">スタイル ウィンドウのオートコンプリート UI\*\*\*\* で[、元に][MDNRevert]戻す CSS キーワードが検出され、プロパティのカスケード値が要素のスタイル設定に適用された以前の値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="1334a-215">The autocomplete UI of the **Styles** pane now detects the [revert][MDNRevert] CSS keyword, which reverts the cascaded value of a property to the previous value applied to the styling of the element.</span></span>  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="プロパティの値を元に戻す設定" lightbox="../../media/2020/05/revert.msft.png":::
  <span data-ttu-id="1334a-217">プロパティの値を元に戻す設定</span><span class="sxs-lookup"><span data-stu-id="1334a-217">Setting the value of a property to revert</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-218">Chromiumの問題[#1075437][CR1075437]</span><span class="sxs-lookup"><span data-stu-id="1334a-218">Chromium issue [#1075437][CR1075437]</span></span>  

#### <a name="image-previews"></a><span data-ttu-id="1334a-219">画像のプレビュー</span><span class="sxs-lookup"><span data-stu-id="1334a-219">Image previews</span></span>  

<span data-ttu-id="1334a-220">[スタイル] `background-image` ウィンドウの値に **カーソルを合** わせると、ツールヒントに画像のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-220">Hover on a `background-image` value in the **Styles** pane to display a preview of the image in a tooltip.</span></span>  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="背景画像の値にカーソルを合わせる" lightbox="../../media/2020/05/image-preview.msft.png":::
  <span data-ttu-id="1334a-222">値の上にカーソルを移動 `background-image` する</span><span class="sxs-lookup"><span data-stu-id="1334a-222">Hovering over a `background-image` value</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-223">Chromium[の問題][CR1040019]#1040019</span><span class="sxs-lookup"><span data-stu-id="1334a-223">Chromium issue [#1040019][CR1040019]</span></span>  

#### <a name="color-picker-now-uses-space-separated-functional-color-notation"></a><span data-ttu-id="1334a-224">カラー ピッカーでスペース区切りの機能色表記が使用される</span><span class="sxs-lookup"><span data-stu-id="1334a-224">Color Picker now uses space-separated functional color notation</span></span>  

<span data-ttu-id="1334a-225">[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] は、スペースで区切られた引数をサポートするカラー関数 (など) `rgb()` を指定します。</span><span class="sxs-lookup"><span data-stu-id="1334a-225">[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] specifies that color functions, such as `rgb()`, should support space-separated arguments.</span></span>  <span data-ttu-id="1334a-226">たとえば、`rgb(0, 0, 0)` は `rbg(0 0 0)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="1334a-226">For example, `rgb(0, 0, 0)` is equivalent to `rbg(0 0 0)`.</span></span>  

<span data-ttu-id="1334a-227">[色の選択][][DevtoolsCssReferenceColorPicker]ウィンドウで色を選択するか、[スタイル] ウィンドウ\*\*\*\* で色表現を交互に選択する場合は、値を保持して選択すると、スペースで区切られた引数構文 `Shift` `background-color` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-227">When you choose colors with the [Color Picker][DevtoolsCssReferenceColorPicker] or alternate between color representations in the **Styles** pane by holding `Shift` and selecting the `background-color` value, the space-separated argument syntax is displayed.</span></span>  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="[スタイル] ウィンドウでのスペース区切り引数の使用" lightbox="../../media/2020/05/color.msft.png":::
  <span data-ttu-id="1334a-229">[スタイル] ウィンドウでのスペース区切り引数 **の** 使用</span><span class="sxs-lookup"><span data-stu-id="1334a-229">Using space-separated arguments in the **Styles** pane</span></span>  
:::image-end:::  

<span data-ttu-id="1334a-230">また、[計算済み] ウィンドウと [ **検査** モード] ツールヒントにも **構文を表示する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="1334a-230">You should also display the syntax in the **Computed** pane and the **Inspect Mode** tooltip.</span></span>  

<span data-ttu-id="1334a-231">Microsoft Edge[Color()][CSSWGDraftsColor4Property]などの今後の CSS 機能では、廃止されたコンマ区切り引数構文がサポートされないので、DevTools は新しい構文を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1334a-231">Microsoft Edge DevTools is using the new syntax because upcoming CSS features such as [color()][CSSWGDraftsColor4Property] do not support the deprecated comma-separated argument syntax.</span></span>  

<span data-ttu-id="1334a-232">スペースで区切られた引数の構文は、ほとんどのブラウザーでしばらくサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1334a-232">The space-separated argument syntax has been supported in most browsers for a while.</span></span>  <span data-ttu-id="1334a-233">詳細については、「使用できる:スペースで区切られた機能の色表記 [」に移動します。][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span><span class="sxs-lookup"><span data-stu-id="1334a-233">For more information, navigate to [Can I use: Space-separated functional color notations?][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span></span>  

<span data-ttu-id="1334a-234">Chromium[問題#1072952][CR1072952]</span><span class="sxs-lookup"><span data-stu-id="1334a-234">Chromium issue [#1072952][CR1072952]</span></span>  

### <a name="deprecation-of-the-properties-pane-in-the-elements-panel"></a><span data-ttu-id="1334a-235">[要素] パネルの [プロパティ] ウィンドウの廃止</span><span class="sxs-lookup"><span data-stu-id="1334a-235">Deprecation of the Properties pane in the Elements panel</span></span>  

<span data-ttu-id="1334a-236">[ **要素]** ツールの **[プロパティ] ウィンドウ** は非推奨です。</span><span class="sxs-lookup"><span data-stu-id="1334a-236">The **Properties** pane in the **Elements** tool is deprecated.</span></span>  <span data-ttu-id="1334a-237">代 `console.dir($0)` わりにコンソール **で** 実行します。</span><span class="sxs-lookup"><span data-stu-id="1334a-237">Run `console.dir($0)` in the **Console** instead.</span></span>  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="非推奨の [プロパティ] ウィンドウ" lightbox="../../media/2020/05/properties.msft.png":::
   <span data-ttu-id="1334a-239">非推奨の **[プロパティ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1334a-239">The deprecated **Properties** pane</span></span>  
:::image-end:::  

#### <a name="references"></a><span data-ttu-id="1334a-240">参考資料</span><span class="sxs-lookup"><span data-stu-id="1334a-240">References</span></span>  

*   [<span data-ttu-id="1334a-241">console.dir()</span><span class="sxs-lookup"><span data-stu-id="1334a-241">console.dir()</span></span>][DevtoolsConsoleApiDir]  
*   [<span data-ttu-id="1334a-242">$0</span><span class="sxs-lookup"><span data-stu-id="1334a-242">$0</span></span>][DevtoolsConsoleUtilitiesDom]  

### <a name="app-shortcuts-support-in-the-manifest-pane"></a><span data-ttu-id="1334a-243">マニフェスト ウィンドウでのアプリ ショートカットのサポート</span><span class="sxs-lookup"><span data-stu-id="1334a-243">App shortcuts support in the Manifest pane</span></span>  

<span data-ttu-id="1334a-244">アプリのショートカット を使用すると、Web アプリ内で一般的または推奨されるタスクをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="1334a-244">App shortcuts help users quickly start common or recommended tasks within a web app.</span></span>  <span data-ttu-id="1334a-245">アプリのショートカット メニューは、ユーザーのデスクトップまたはモバイル デバイスにインストールされている [プログレッシブ Web][PwaIndex] アプリにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-245">The app shortcuts menu is shown only for [Progressive Web Apps][PwaIndex] that are installed on the user's desktop or mobile device.</span></span>  

<!--For more information, navigate to [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="マニフェスト ウィンドウのアプリ ショートカット" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  <span data-ttu-id="1334a-247">マニフェスト ウィンドウのアプリ**ショートカット**</span><span class="sxs-lookup"><span data-stu-id="1334a-247">App shortcuts in the **Manifest** pane</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="1334a-248">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="1334a-248">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="1334a-249">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1334a-249">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="1334a-250">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1334a-250">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="1334a-251">Devtools チームとMicrosoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="1334a-251">Getting in touch with Microsoft Edge Devtools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/settings-icon.msft.png  
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/toggle-screencast-icon.msft.png  
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/refresh-page-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/record-icon.msft.png  

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用|Microsoft Docs"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "カラー ピッカー - CSS リファレンス を使用して色を変更|Microsoft Docs"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - カスタマイズの概要|Microsoft Docs"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "DevTools の [問題] タブの [Microsoft Edgeを検索して修正|Microsoft Docs"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "はじめに リモート デバッグ Android デバイスの使用|Microsoft Docs"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "はじめに Surface Duo エミュレーターの使用|Microsoft Docs"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモート デバッグの概要 | Microsoft Docs"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "リソース リソースの詳細を調|Microsoft Docs"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワーク アクティビティのログ |Microsoft Docs"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "プログレッシブ Web Apps on Windows |Microsoft Docs"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft EdgeAndroid アプリ"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "スペースで区切られた機能的な色表記 - MDN |使用できる"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可|Chromiumバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準拠の|Chromiumバグ"  
[CR1040019]: https://crbug.com/1040019 "DevTools: [スタイル] ウィンドウの [スタイル] ウィンドウで画像と背景画像を簡単にプレビュー|Chromiumバグ"  
[CR1040025]: https://crbug.com/1040025 "DevTools: 要素ポップオーバー の基本 a11y 情報を表示|Chromiumバグ"  
[CR1048378]: https://crbug.com/1048378 "ハイ コントラスト モードの DevTools UI の|Chromiumバグ"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromiumバグ"  
[CR1068116]: https://crbug.com/1068116 "[出荷の問題] パネル|Chromiumバグ"  
[CR1072952]: https://crbug.com/1072952 "DevTools: カラー ピッカーは、最新の CSS カラー構文を生成|Chromiumバグ"  
[CR1075437]: https://crbug.com/1075437 "DevTools: CSS 'revert' キーワード/値のサポートを追加|Chromiumバグ"  
[CR1076112]: https://crbug.com/1076112 "Devtools 個人用設定 - ドロワーリサイズ"  
[CR1081486]: https://crbug.com/1081486 "スクリーンキャスト モードのナビゲーション ボタンにキーボード フォーカスが表示されない|Chromiumバグ"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus は 'fulfilled' で、&quot;解決済み&quot; の|V8 のバグ"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "色 3 からの変更 - CSS カラー モジュール レベル 4 |W3C CSS ワーキング グループ エディターの下書き"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. 前景色: 'color' - CSS Color Module Level 4 |W3C CSS ワーキング グループ エディターの下書き"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新しい機能のMicrosoft Edge"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "状態と運命 - domenic/promises-unwrapping |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "元に戻す|MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "ブラウザーの互換性|MDN"  

[VisualStudioCode]: https://code.visualstudio.com/ "Visual Studio Code"  
[VisualStudioCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Code の Windows 用キーボード ショートカット"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "Axe: キーボード |WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "Axe: Name Role Value |WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "ハイ コントラスト モードのオンとオフを切り替Windows |Windowsサポート"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edgeプレビュー チャネル"  
[TheWebWeWant]: https://aka.ms/webwewant "必要とされる Web"  

<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebdevCoreWebVitals]: https://alphabet-dev/vitals#core-web-vitals "Core Web Vitals | alphabet-dev"  -->  

> [!NOTE]
> <span data-ttu-id="1334a-296">このページの一部は、[Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更であり、「[Creative Commons Attribution 4.0 International License][CCA4IL]」に記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1334a-296">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1334a-297">元のページは [ここ](https://developer.chrome.com/blog/new-in-devtools-84) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="1334a-297">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-84) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1334a-299">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1334a-299">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
