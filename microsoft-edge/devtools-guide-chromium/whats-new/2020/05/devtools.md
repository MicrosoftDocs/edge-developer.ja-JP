---
title: DevTools の新機能 (Microsoft Edge 84)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: aa39e5d7811d4a614e055a8e0479c74278efbefd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942185"
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

# <span data-ttu-id="1ce6c-103">DevTools の新機能 (Microsoft Edge 84)</span><span class="sxs-lookup"><span data-stu-id="1ce6c-103">What's new in DevTools (Microsoft Edge 84)</span></span>  

## <span data-ttu-id="1ce6c-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="1ce6c-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="1ce6c-105">以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="1ce6c-106">デベロッパー、VS コード拡張機能などで新機能を試すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="1ce6c-107">開発者ツールの最新機能と最大の機能をすべて最新の状態に保つためには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを [ダウンロードし、Twitter でフォローしてください][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="1ce6c-108">Windows ハイ コントラスト モードで DevTools を使用する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-108">Use the DevTools in Windows high contrast mode</span></span>

<span data-ttu-id="1ce6c-109">Windows がハイコントラスト モードの場合、Microsoft Edge DevTools がハイ コントラスト モードで表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-109">The Microsoft Edge DevTools are now displayed in high contrast mode when Windows is in high contrast mode.</span></span>  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="ハイ コントラスト モードの Microsoft Edge DevTools" lightbox="../../media/2020/05/high-contrast.msft.png":::
   <span data-ttu-id="1ce6c-111">ハイ コントラスト モードの Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="1ce6c-111">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-112">[指示に従って、Windows のハイ コントラスト モードをオンにします][MicrosoftSupportWindows10HighContrastMode]。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-112">[Follow the instructions to turn on high contrast mode in Windows][MicrosoftSupportWindows10HighContrastMode].</span></span>  <span data-ttu-id="1ce6c-113">Microsoft Edge で DevTools を開くには、キーを押すか、キーを `F12` 押します `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-113">Open the DevTools in Microsoft Edge by pressing `F12` or `Ctrl`+`Shift`+`I`.</span></span>  <span data-ttu-id="1ce6c-114">ハイ コントラスト モードで DevTools が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-114">The DevTools are displayed in high contrast mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="1ce6c-115">現在 Microsoft Edge DevTools は現在、Windows でハイ コントラスト モードをサポートしていますが、macOS ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-115">The Microsoft Edge DevTools currently support high contrast mode on Windows but not on macOS.</span></span> 

<span data-ttu-id="1ce6c-116">Chromium の [問題#1048378][CR1048378]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-116">Chromium issue [#1048378][CR1048378]</span></span>  

### <span data-ttu-id="1ce6c-117">DevTools のキーボード ショートカットを VS コードに一致する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-117">Match keyboard shortcuts in the DevTools to VS Code</span></span>  

<span data-ttu-id="1ce6c-118">お客様の [フィードバックと](#getting-in-touch-with-microsoft-edge-devtools-team) [Chromium パ][CRIssuesList]ブリックの問題トラッカーから、DevTools でキーボード ショートカットをカスタマイズできるようにしたい Microsoft Edge DevTools チームからお客様のフィードバックをお寄せいただけます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-118">From your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) and the [Chromium public issue tracker][CRIssuesList], the Microsoft Edge DevTools team learned that you wanted the ability to customize keyboard shortcuts in the DevTools.</span></span>  <span data-ttu-id="1ce6c-119">Microsoft Edge 84 では、デベロッパーツールのキーボード ショートカットを [VS コードに][VSCode]対応できるようになりました。これは、チームが作業している機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-119">In Microsoft Edge 84, you are now able to match keyboard shortcuts in the DevTools to [VS Code][VSCode], which is just one of the features the team is working on for shortcut customization.</span></span>  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="DevTools のキーボード ショートカットを VS コードに一致する" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   <span data-ttu-id="1ce6c-121">ハイ コントラスト モードの Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="1ce6c-121">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-122">試してみるには、DevTools の右上隅にある [DevTools の設定] アイコンアイコンを押するか `?` ![ ][ImageSettingsIcon] 、選択します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-122">To try the experiment, open DevTools Settings by pressing `?` or selecting the ![DevTools Settings icon][ImageSettingsIcon] icon in the top-right corner of the DevTools.</span></span>  <span data-ttu-id="1ce6c-123">[環境設定]**セクションに移動し**、[カスタム キーボード ショートカットの**設定] タブを有効にする (再読み込む必要があります)。**</span><span class="sxs-lookup"><span data-stu-id="1ce6c-123">Navigate to the **Experiments** section and check **Enable custom keyboard shortcuts settings tab (requires reload)**.</span></span>  <span data-ttu-id="1ce6c-124">開発ツールを再読み込みし、[設定] をもう一度開き、ショートカット セクション **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-124">Now reload the DevTools, open Settings again, and navigate to the **Shortcuts** section.</span></span>  

<span data-ttu-id="1ce6c-125">事**前設定されている [一致] ショートカットのドロップダウンから [DevTools](既定)** を選択し、[コード **] Visual Studioします**。 **Match shortcuts from preset**</span><span class="sxs-lookup"><span data-stu-id="1ce6c-125">Select **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="1ce6c-126">DevTools のキーボード ショートカットが VS コード内の等当な操作のショートカットと一致できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-126">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in VS Code.</span></span>  

<span data-ttu-id="1ce6c-127">たとえば、VS コードでスクリプトを一時的に実行または実行するためのキーボード [ショートカットは、次のとおり][VSCodeShortcuts] です `F5` 。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-127">For example, the keyboard shortcut for pausing or continuing running a script in [VS Code][VSCodeShortcuts] is `F5`.</span></span>  <span data-ttu-id="1ce6c-128">**DevTools (既定)** のプリセットでは、DevTools で同じショートカットが `F8` あっても **、Visual Studio Code**の事前設定でもそのショートカットがインストールされています `F5` 。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-128">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8` but with the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="1ce6c-129">現在この機能は Microsoft Edge 84 で実用的な機能を実現しているため、フィードバックを [チームと共有](#getting-in-touch-with-microsoft-edge-devtools-team) してください。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-129">The feature is currently available in Microsoft Edge 84 as an experiment, so please share your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) with the team!</span></span>  

<span data-ttu-id="1ce6c-130">Chromium の [問題#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-130">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="1ce6c-131">リモート デバッグ Surface Duo エミュレーター</span><span class="sxs-lookup"><span data-stu-id="1ce6c-131">Remote debug Surface Duo emulators</span></span>  

<span data-ttu-id="1ce6c-132">[Microsoft Edge DevTools][DevToolsChromiumGuide]の完全機能を利用し[、Surface Duo エ][DualScreensAndroidEmulator]ミュレーターで実行されている Web コンテンツをリモートでデバッグできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-132">You are now able to remotely debug your web content running in the [Surface Duo emulator][DualScreensAndroidEmulator] using the full power of the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

<span data-ttu-id="1ce6c-133">Surface [Duo エミュレータ][DualScreensAndroidEmulator]ーでは、新しいフォールドやデュアルスクリーン デバイスの新しいクラスで Web コンテンツのレンダリング方法をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-133">With the [Surface Duo emulator][DualScreensAndroidEmulator], you are able to test how your web content renders on a new class of foldable and dual-screen devices.</span></span>  <span data-ttu-id="1ce6c-134">エミュレーターは Android オペレーティング システムを実行し [、Microsoft Edge Android アプリを提供します][AndroidEdge]。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-134">The emulator runs the Android operating system and provides the [Microsoft Edge Android app][AndroidEdge].</span></span>  <span data-ttu-id="1ce6c-135">Microsoft Edge アプリで Web コンテンツを読 [み込][AndroidEdge] み [、Microsoft Edge DevTools でデバッグします][DevToolsChromiumGuide]。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-135">Load your web content in the [Microsoft Edge app][AndroidEdge] and debug it with the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="Surface Duo エミュレーター上で実行されている Microsoft Edge アプリ" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   <span data-ttu-id="1ce6c-137">Surface Duo エミュレーター上の Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="1ce6c-137">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-138">Microsoft Edge のデスクトップ インスタンスには `edge://inspect` **、Surface DuoEmulator**上で実行されている開いているタブ[または PWA の][PwaIndex]一覧が[表示されます][DualScreensAndroidEmulator]。 [Microsoft Edge][DesktopEdge]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-138">The `edge://inspect` page in a desktop instance of [Microsoft Edge][DesktopEdge] shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaIndex] that are running on the [Surface Duo emulator][DualScreensAndroidEmulator].</span></span>  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="エedge://inspectージ モリューターで実行されている Microsoft Edge アプリで開いているタブのリストが表示されます。" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   <span data-ttu-id="1ce6c-140">ページには、エミュレーター上で実行されている Microsoft Edge アプリで開いているタブの `edge://inspect` リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-140">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>
:::image-end:::  

<span data-ttu-id="1ce6c-141">デ **バッグする** タブまたは PWA について検査を選択すると [、Microsoft Edge DevTools が開きます][DevToolsChromiumGuide]。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-141">Selecting **inspect** for the tab or PWA that you want to debug opens the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  <span data-ttu-id="1ce6c-142">[Surface Duo エミュレ][DevToolsRemoteDebugDuoEmulator]ーター上の Web コンテンツをリモートでデバッグするには、ステップ バイ ステップ ガイドに従います。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-142">[Follow the step-by-step guide to remotely debug your web content on the Surface Duo emulator][DevToolsRemoteDebugDuoEmulator].</span></span>  

### <span data-ttu-id="1ce6c-143">より簡単に DevTools 図面のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-143">Resize the DevTools drawer more easily</span></span>  

<span data-ttu-id="1ce6c-144">Microsoft Edge 83 以前では、描画ツールのツール バー内を [移動して DevTools Drawer][DevToolsDrawer] のサイズを変更することができました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-144">In Microsoft Edge 83 or earlier, you were only able to resize the [DevTools Drawer][DevToolsDrawer] by hovering inside the Drawer's toolbar.</span></span>  <span data-ttu-id="1ce6c-145">図面の機能は、ウィンドウの境界線をマウスで置くと、サイズを変更する開発ツールのウィンドウのその他のサイズ変更コントロールとは異なります。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-145">The Drawer behaved differently than the other resize controls for panes in the DevTools where you hover over the border of the pane to resize it.</span></span>  <span data-ttu-id="1ce6c-146">次の画像を選択して、83 以前の Microsoft Edge での図面のサイズ変更方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-146">Select the following image to see how resizing the Drawer worked in version 83 or earlier of Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="Microsoft Edge 83 で DevTools Drawer のサイズを変更する" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   <span data-ttu-id="1ce6c-148">Microsoft Edge 83 で DevTools Drawer のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-148">Resizing the DevTools Drawer in Microsoft Edge 83</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="1ce6c-149">Microsoft Edge 84 以降では、描画ツールの枠線の上にマウス ポインターを合わせると、描画パターのサイズを変更できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-149">Starting with Microsoft Edge 84, you are now able to resize the Drawer by hovering over the border of the Drawer.</span></span>  <span data-ttu-id="1ce6c-150">これにより、DevTools の図面のサイズ変更と、DevTools の他のウィンドウ サイズを変更する方法で、DevTools Drawer のサイズ変更が行えます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-150">This change aligns the behavior resizing the DevTools Drawer with the way you resize other panes in the DevTools.</span></span>  <span data-ttu-id="1ce6c-151">次の画像を選択して、Microsoft Edge 84 での動作のサイズ変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-151">Select the following image to see resizing in action in Microsoft Edge 84.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="Microsoft Edge 84 で DevTools Drawer のサイズを変更する" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   <span data-ttu-id="1ce6c-153">Microsoft Edge 84 で DevTools Drawer のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-153">Resizing the DevTools Drawer in Microsoft Edge 84</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="1ce6c-154">Chromium の問題 [#1076112][CR1076112]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-154">Chromium issue [#1076112][CR1076112]</span></span>  

### <span data-ttu-id="1ce6c-155">ナビゲーション ボタンのフォーカスが表示される画面キャッシュ</span><span class="sxs-lookup"><span data-stu-id="1ce6c-155">Screencasting navigation buttons display focus</span></span>  

<span data-ttu-id="1ce6c-156">[Android][DevToolsRemoteDebugAndroid]デバイス[、Windows 10][DevToolsRemoteDebugWindows]デバイス、[または Surface Duo エ][DevToolsRemoteDebugDuoEmulator]ミュレーターのリモート デバッグを行う場合、DevTools の左上隅にある [画面の切り替え] アイコンを使用して画面キャストを切 ![ ][ImageScreencastingIcon] り替えられます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-156">When remote debugging an [Android device][DevToolsRemoteDebugAndroid], a [Windows 10 device][DevToolsRemoteDebugWindows], or a [Surface Duo emulator][DevToolsRemoteDebugDuoEmulator], you are able to toggle screencasting with the ![Toggle Screencast][ImageScreencastingIcon] icon in the top-left corner of the DevTools.</span></span>  <span data-ttu-id="1ce6c-157">画面が有効になっている場合は、DevTools ウィンドウからリモート デバイスの Microsoft Edge のタブ間を移動することができます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-157">With screencasting enabled, you are able to navigate the tab in Microsoft Edge on the remote device from the DevTools window.</span></span>  <span data-ttu-id="1ce6c-158">Microsoft Edge 84 では、これらのナビゲーション ボタンにもキーボードがアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-158">In Microsoft Edge 84, these navigation buttons are now also keyboard accessible.</span></span>  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="画面に表示された URL バーから Shift + Tab キーを押すと、[更新] ボタンにフォーカスが表示されます。" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   <span data-ttu-id="1ce6c-160">スクリーンキ `Shift` + `Tab` ャストした URL バーから押すと、[更新] ボタンにフォーカスが**表示**されます</span><span class="sxs-lookup"><span data-stu-id="1ce6c-160">Pressing `Shift`+`Tab` from the screencasted URL bar shows focus on the **Refresh** button</span></span>
:::image-end:::  

<span data-ttu-id="1ce6c-161">Chromium の [問題はc#1081486][CR1081486]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-161">Chromium issue [#1081486][CR1081486]</span></span>  

### <span data-ttu-id="1ce6c-162">ネットワーク パネルの詳細ウィンドウにアクセスできるようになりました</span><span class="sxs-lookup"><span data-stu-id="1ce6c-162">Network panel Details pane is now accessible</span></span>  

<span data-ttu-id="1ce6c-163">Microsoft Edge 84 では[、[ネットワーク][DevToolsNetworkDetails]ログ**Network**] でリソースを開くと、[ネットワーク パネルの詳細] ウィンドウがフォーカスされる[ようになりました][DevToolsNetworkLog]。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-163">In Microsoft Edge 84, the [Details pane][DevToolsNetworkDetails] in the **Network** panel now takes focus when you open it for a resource in the [Network Log][DevToolsNetworkLog].</span></span>  <span data-ttu-id="1ce6c-164">この変更により、スクリーン リーダーは詳細ウィンドウの内容を読み取り、操作**することができます。**</span><span class="sxs-lookup"><span data-stu-id="1ce6c-164">This change allows screen readers to read out and interact with the content of the **Details** pane.</span></span>  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="開いたときに、ネットワーク パネルの詳細ウィンドウがフォーカスされた状態で移動します。" lightbox="../../media/2020/05/network-details.msft.png":::
   <span data-ttu-id="1ce6c-166">開 **いた** ときに **、ネットワーク** パネルの詳細ウィンドウがフォーカスされた状態で移動します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-166">The **Details** pane in the **Network** panel takes focus when opened</span></span>
:::image-end:::  

<span data-ttu-id="1ce6c-167">Chromium の問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-167">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="1ce6c-168">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="1ce6c-168">Announcements from the Chromium project</span></span>  

<span data-ttu-id="1ce6c-169">次のセクションでは、オープン ソース Chromium プロジェクトに投稿された Microsoft Edge 84 で利用可能なその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-169">The following sections announce additional features available in Microsoft Edge 84 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="1ce6c-170">DevTools 図面の新しい問題ツールでサイトの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-170">Fix site issues with the new Issues tool in the DevTools Drawer</span></span>

<span data-ttu-id="1ce6c-171">DevTools **図面の** 新しい問題ツールが、本体の通知のフトラッシュと集中性を下 **げるのに役立てました**。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-171">The new **Issues** tool in the DevTools Drawer was built to help reduce the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="1ce6c-172">現在、 **本体** は Web サイトの開発者、ライブラリ、フレームワーク、および Microsoft Edge がメッセージ、警告、エラーをログに記録する中間的な場所です。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-172">Currently, the **Console** is the central place for website developers, libraries, frameworks, and Microsoft Edge to log messages, warnings, and errors.</span></span>  <span data-ttu-id="1ce6c-173">**問題ツール**は、構造化、集約、実行可能な方法でブラウザーからの警告を集約し、Microsoft Edge DevTools 内の影響を受けるリソースへのリンク、問題の修正方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-173">The **Issues** tool aggregates warnings from the browser in a structured, aggregated, and actionable way, links to affected resources within Microsoft Edge DevTools, and provides guidance on how to fix the issues.</span></span>  <span data-ttu-id="1ce6c-174">本体の問題に対する Microsoft Edge の警告は本体より **も問題** ツールで表示されるようになるため **、** 本体での余分な機能を下げる **のに役立ちます**。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-174">Over time, you should see more and more warnings in Microsoft Edge surfacing in the **Issues** tool rather than the **Console**, which should help reduce the clutter in the **Console**.</span></span>  

<span data-ttu-id="1ce6c-175">使用を開始するには [、Microsoft Edge DevTools の][DevtoolsIssuesIndex]問題ツールに関する問題を見つして修正します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-175">To get started, see [Find And Fix Problems With The Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools 図面の問題ツール" lightbox="../../media/2020/05/issues.msft.png":::
   <span data-ttu-id="1ce6c-177">**DevTools**図面の問題ツール</span><span class="sxs-lookup"><span data-stu-id="1ce6c-177">The **Issues** tool in the DevTools Drawer</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-178">Chromium の [問題#1068116][CR1068116]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-178">Chromium issue [#1068116][CR1068116]</span></span>  

### <span data-ttu-id="1ce6c-179">検査モードのヒントでアクセシビリティ情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-179">View accessibility information in the Inspect Mode tooltip</span></span>  

<span data-ttu-id="1ce6c-180">検 **査モードのヒン** トは、要素にアクセス可能な名前がで、 [キーボード][WebhintHintsAxeNameRoleValue] フォーカスがあるかどうか [を示します][WebhintHintsAxeKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-180">The **Inspect Mode** tooltip now indicates whether the element has an accessible [name and role][WebhintHintsAxeNameRoleValue] and is [keyboard-focusable][WebhintHintsAxeKeyboard].</span></span>  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="アクセシビリティ情報が含された検査モードのヒント" lightbox="../../media/2020/05/a11y.msft.png":::
  <span data-ttu-id="1ce6c-182">アクセシビリティ **情報が含された** 検査モードのヒント</span><span class="sxs-lookup"><span data-stu-id="1ce6c-182">The **Inspect Mode** tooltip with accessibility information</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-183">Chromium の問題はキ [#1040025][CR1040025]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-183">Chromium issue [#1040025][CR1040025]</span></span>  

### <span data-ttu-id="1ce6c-184">パフォーマンス パネルの更新</span><span class="sxs-lookup"><span data-stu-id="1ce6c-184">Performance panel updates</span></span>  

#### <span data-ttu-id="1ce6c-185">フッターに "禁止時間" の情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-185">View Total Blocking Time information in the footer</span></span>  

<span data-ttu-id="1ce6c-186">読み込みのパフォーマンス を記録すると、 **パフ** ォーマンス パネルにフッターに "ブロック時間 "合計ブロック時間 \(TBT\) の情報が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-186">After recording your load performance, the **Performance** panel now shows Total Blocking Time \(TBT\) information in the footer.</span></span>  <span data-ttu-id="1ce6c-187">TBT は読み込みのパフォーマンス メトリックで、ページが使用可能になった時間を数量にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-187">TBT is a load performance metric that helps quantify how long a page takes to become usable.</span></span>  <span data-ttu-id="1ce6c-188">コンテンツは画面\にレンダリングされるため、ページが使用可能な時間を測定します (コンテンツは画面\にレンダリングされるため)。ただし、JavaScript がメイン スレッドをブロックしているため、ページはユーザー入力に応答しないため、実際に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-188">It essentially measures how long a page appears to be usable \(because the content is rendered to the screen\); but is not actually usable, because JavaScript is blocking the main thread and therefore the page does not respond to user input.</span></span>  <span data-ttu-id="1ce6c-189">TBT は、First Input Delay におおおるメトリックです。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-189">TBT is the main metric for approximating First Input Delay.</span></span>  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

<span data-ttu-id="1ce6c-190">総ブロック時間情報を取得するには、[ページの読み**Refresh Page**込み時の更新] アイコン ワークフローを使用してページ読み込みのパフォー ![ ][ImageRefreshPageIcon] マンスを記録しないでください。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-190">To get Total Blocking Time information, do not use the **Refresh Page** ![Refresh page icon][ImageRefreshPageIcon] workflow for recording page load performance.</span></span>  

<span data-ttu-id="1ce6c-191">代わりに、[ **レコード録音]** アイコン ![ を ][ImageRecordIcon] 選択し、ページを手動で再読み込み、ページが読み込みの待ってから記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-191">Instead, select **Record** ![Record icon][ImageRecordIcon], manually reload the page, wait for the page to load, and then stop recording.</span></span>  

<span data-ttu-id="1ce6c-192">表示されていなかった場合、Microsoft Edge DevTools は内部プロファイリング データから必要な情報を `Total Blocking Time: Unavailable` 取得しませんでした。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-192">If you see `Total Blocking Time: Unavailable`, Microsoft Edge DevTools did not get the required information from the internal profiling data in Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="パフォーマンス パネルの記録のフッターの [ブロック時間] の合計情報" lightbox="../../media/2020/05/tbt.msft.png":::
   <span data-ttu-id="1ce6c-194">パフォーマンス パネルの記録のフッターの [ **ブロック** 時間] の合計情報</span><span class="sxs-lookup"><span data-stu-id="1ce6c-194">Total Blocking Time information in the footer of a **Performance** panel recording</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-195">Chromium の問題は、chromium [の#1054381][CR1054381]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-195">Chromium issue [#1054381][CR1054381]</span></span>  

#### <span data-ttu-id="1ce6c-196">新しいエクスペリエンス セクションのレイアウト シフト イベント</span><span class="sxs-lookup"><span data-stu-id="1ce6c-196">Layout Shift events in the new Experience section</span></span>  

<span data-ttu-id="1ce6c-197">パフォ**ーマン\*\*\*\*ス**パネルの新しい [エクスペリエンス] セクションを使用すると、レイアウト シフトを検出できます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-197">The new **Experience** section of the **Performance** panel helps you detect layout shifts.</span></span>  <span data-ttu-id="1ce6c-198">累積レイアウトシフト \(CLS\) は、不必要な視覚的なインストーリーを検出するのに役立つメトリックです。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-198">Cumulative Layout Shift \(CLS\) is a metric that helps you quantify unwanted visual instability.</span></span>

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

<span data-ttu-id="1ce6c-199">[レイアウト シ **フト]** イベントを選択すると、概要ウィンドウにレイアウト シフトの詳細 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-199">Select the **Layout Shift** event to see the details of the layout shift in the **Summary** pane.</span></span>  <span data-ttu-id="1ce6c-200">[移動] と [ **移動した** ] フィールド **にカーソ** ルを合って、レイアウトシフトが発生した位置を視覚化します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-200">Hover over the **Moved from** and **Moved to** fields to visualize where the layout shift occurred.</span></span>  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="レイアウト シフトの詳細" lightbox="../../media/2020/05/cls.msft.png":::
   <span data-ttu-id="1ce6c-202">レイアウト シフトの詳細</span><span class="sxs-lookup"><span data-stu-id="1ce6c-202">The details of a layout shift</span></span>  
:::image-end:::  

### <span data-ttu-id="1ce6c-203">本体での正確なプロミス用語</span><span class="sxs-lookup"><span data-stu-id="1ce6c-203">More accurate promise terminology in the Console</span></span>  

<span data-ttu-id="1ce6c-204">ログ記録時に、 `Promise` **本体が** 誤って提供された `PromiseStatus` 値を設定していません `resolved` 。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-204">When logging a `Promise`, the **Console** incorrectly provided `PromiseStatus` value set to `resolved`.</span></span>  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="古い解決用語を使用した本体の例" lightbox="../../media/2020/05/resolved.msft.png":::
   <span data-ttu-id="1ce6c-206">古い用 **語を** 使用した本体 `resolved` の例</span><span class="sxs-lookup"><span data-stu-id="1ce6c-206">An example of the **Console** using the old `resolved` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-207">本 **体では** 用語が使用され、指定した用語と `fulfilled` 合わせて配置 `Promise` されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-207">The **Console** now uses the term `fulfilled`, which aligns with the `Promise` specification.</span></span>  <span data-ttu-id="1ce6c-208">具体名の詳細 `Promise` については [、GitHub の「都道府県」と「Fates」を参照してください](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-208">For more information about the `Promise` specification, see [States and Fates on GitHub](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md).</span></span>  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="新しいフルフィルフィルタされた用語を使用した本体の例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  <span data-ttu-id="1ce6c-210">新しい用 **語を使用** した本 `fulfilled` 体の例</span><span class="sxs-lookup"><span data-stu-id="1ce6c-210">An example of the **Console** using the new `fulfilled` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-211">V8 の [問題#6751][CRV86751]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-211">V8 issue [#6751][CRV86751]</span></span>  

### <span data-ttu-id="1ce6c-212">[スタイル] ウィンドウの更新</span><span class="sxs-lookup"><span data-stu-id="1ce6c-212">Styles pane updates</span></span>  

#### <span data-ttu-id="1ce6c-213">リバート キーワードのサポート</span><span class="sxs-lookup"><span data-stu-id="1ce6c-213">Support for the revert keyword</span></span>  

<span data-ttu-id="1ce6c-214">[スタイル] ウィンドウのオ**Styles**ートコンプリート[UI][MDNRevert]で、要素のスタイリングに適用された、プロパティのカスケード値を前の値に戻します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-214">The autocomplete UI of the **Styles** pane now detects the [revert][MDNRevert] CSS keyword, which reverts the cascaded value of a property to the previous value applied to the styling of the element.</span></span>  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="戻すプロパティの値を設定する" lightbox="../../media/2020/05/revert.msft.png":::
  <span data-ttu-id="1ce6c-216">戻すプロパティの値を設定する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-216">Setting the value of a property to revert</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-217">Chromium [の問題#1075437][CR1075437]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-217">Chromium issue [#1075437][CR1075437]</span></span>  

#### <span data-ttu-id="1ce6c-218">画像のプレビュー</span><span class="sxs-lookup"><span data-stu-id="1ce6c-218">Image previews</span></span>  

<span data-ttu-id="1ce6c-219">[スタイル] ウィンドウの `background-image` 値にマウス ポイン **ターを置** くと、ヒントに画像のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-219">Hover over a `background-image` value in the **Styles** pane to see a preview of the image in a tooltip.</span></span>  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="背景画像の値の上にマウス ポインターを置く" lightbox="../../media/2020/05/image-preview.msft.png":::
  <span data-ttu-id="1ce6c-221">値の上にマウス カーソルを `background-image` 置く</span><span class="sxs-lookup"><span data-stu-id="1ce6c-221">Hovering over a `background-image` value</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-222">Chromium の問題 [#1040019][CR1040019]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-222">Chromium issue [#1040019][CR1040019]</span></span>  

#### <span data-ttu-id="1ce6c-223">[色の選択] で、スペースで区切った関数カラー表を使用する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-223">Color Picker now uses space-separated functional color notation</span></span>  

<span data-ttu-id="1ce6c-224">[CSS カラー モジュール レベル 4 は、スペース][CSSWGDraftsColor4Changes3] 区切り引数をサポートする必要がある、色のモジュール レベル 4 `rgb()` を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-224">[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] specifies that color functions, such as `rgb()`, should support space-separated arguments.</span></span>  <span data-ttu-id="1ce6c-225">たとえば、`rgb(0, 0, 0)` は `rbg(0 0 0)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-225">For example, `rgb(0, 0, 0)` is equivalent to `rbg(0 0 0)`.</span></span>  

<span data-ttu-id="1ce6c-226">[スタイル] ウィンドウで色を選ぶ[か、値][DevtoolsCssReferenceColorPicker]を選んで選択することで色の選択を切り替**Styles**えると、スペース区切り `Shift` 引数の `background-color` 構文が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-226">When you choose colors with the [Color Picker][DevtoolsCssReferenceColorPicker] or alternate between color representations in the **Styles** pane by holding `Shift` and selecting the `background-color` value, you should see the space-separated argument syntax.</span></span>  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="[スタイル] ウィンドウでスペース区切り引数を使用する" lightbox="../../media/2020/05/color.msft.png":::
  <span data-ttu-id="1ce6c-228">[スタイル] ウィンドウでスペース区切り引数 **を使用** する</span><span class="sxs-lookup"><span data-stu-id="1ce6c-228">Using space-separated arguments in the **Styles** pane</span></span>  
:::image-end:::  

<span data-ttu-id="1ce6c-229">また、[コンピュート] ウィンドウと [検**Computed**査モード] のヒントにも**構文**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-229">You should also see the syntax in the **Computed** pane and the **Inspect Mode** tooltip.</span></span>  

<span data-ttu-id="1ce6c-230">Microsoft Edge DevTools では、カラー [(color()][CSSWGDraftsColor4Property] などの CSS 機能では非前の引数の構文をサポートしないため、Microsoft Edge DevTools では新しい構文が使用されています。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-230">Microsoft Edge DevTools is using the new syntax because upcoming CSS features such as [color()][CSSWGDraftsColor4Property] do not support the deprecated comma-separated argument syntax.</span></span>  

<span data-ttu-id="1ce6c-231">スペース区切り引数の構文は、ほとんどのブラウザーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-231">The space-separated argument syntax has been supported in most browsers for a while.</span></span>  <span data-ttu-id="1ce6c-232">詳細については、「スペース区切りの関数の色表にスペース [区切りの表を挿入する」を参照してください。][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-232">For more information, see [Can I use: Space-separated functional color notations?][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span></span>  

<span data-ttu-id="1ce6c-233">Chromium の [問題#1072952][CR1072952]</span><span class="sxs-lookup"><span data-stu-id="1ce6c-233">Chromium issue [#1072952][CR1072952]</span></span>  

### <span data-ttu-id="1ce6c-234">[要素] パネルの [プロパティ] ウィンドウの廃い</span><span class="sxs-lookup"><span data-stu-id="1ce6c-234">Deprecation of the Properties pane in the Elements panel</span></span>  

<span data-ttu-id="1ce6c-235">要素 **パネ** ルの [ **プロパティ** ] ウィンドウは廃減されました。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-235">The **Properties** pane in the **Elements** panel is deprecated.</span></span>  <span data-ttu-id="1ce6c-236">代 `console.dir($0)` わりに **本体で** 実行します。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-236">Run `console.dir($0)` in the **Console** instead.</span></span>  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="非保持されたプロパティ ウィンドウ" lightbox="../../media/2020/05/properties.msft.png":::
   <span data-ttu-id="1ce6c-238">非保持されたプロパティ**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="1ce6c-238">The deprecated **Properties** pane</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ce6c-239">参考資料</span><span class="sxs-lookup"><span data-stu-id="1ce6c-239">References</span></span>  

*   [<span data-ttu-id="1ce6c-240">console.dir()</span><span class="sxs-lookup"><span data-stu-id="1ce6c-240">console.dir()</span></span>][DevtoolsConsoleApiDir]  
*   [<span data-ttu-id="1ce6c-241">$0</span><span class="sxs-lookup"><span data-stu-id="1ce6c-241">$0</span></span>][DevtoolsConsoleUtilitiesDom]  

### <span data-ttu-id="1ce6c-242">[マニフェスト] ウィンドウでのアプリ ショートカット</span><span class="sxs-lookup"><span data-stu-id="1ce6c-242">App shortcuts support in the Manifest pane</span></span>  

<span data-ttu-id="1ce6c-243">アプリ のショートカットにより、ユーザーは Web アプリ内で一般的なまたは推奨タスクをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-243">App shortcuts help users quickly start common or recommended tasks within a web app.</span></span>  <span data-ttu-id="1ce6c-244">アプリのショートカット メニューは、ユーザーのデスクトップまたはモバイル デバイスにインストールされている進行中の [Web アプリ][PwaIndex] に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-244">The app shortcuts menu is shown only for [Progressive Web Apps][PwaIndex] that are installed on the user's desktop or mobile device.</span></span>  

<!--For more information, see [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="マニフェスト ウィンドウのアプリ ショートカット" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  <span data-ttu-id="1ce6c-246">マニフェ**スト ウィンドウのアプリ ショートカット**</span><span class="sxs-lookup"><span data-stu-id="1ce6c-246">App shortcuts in the **Manifest** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="1ce6c-247">Microsoft Edge のプレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="1ce6c-247">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="1ce6c-248">Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-248">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="1ce6c-249">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-249">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="1ce6c-250">Microsoft Edge Devtools チームとのつながりを教える</span><span class="sxs-lookup"><span data-stu-id="1ce6c-250">Getting in touch with Microsoft Edge Devtools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "[開発ツールの設定] アイコン"
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/images/toggle-screencast-icon.msft.png "DevTools の切り替えアイコン"
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png "DevTools のパフォーマンス パネルの [ページの更新] アイコン"
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png "DevTools パフォーマンス パネルの [レコード] アイコン"

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用する |Microsoft ドキュメント"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - 本体 API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - 本体のユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "色の作成で色を変更する - CSS リファレンス |Microsoft ドキュメント"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "[図形描画] - 概要のカスタマイズ |Microsoft ドキュメント"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の問題タブに関する問題を見つけ、解決する |Microsoft ドキュメント"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "リモート デバッグの Android デバイスの使用を開始する |Microsoft ドキュメント"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "Surface Duo エミュレーターのリモート デバッグの使用を開始する |Microsoft ドキュメント"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモート デバッグの使用を開始する |Microsoft ドキュメント"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "リソースの詳細を検査する |Microsoft ドキュメント"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワーク アクティビティを記録する |Microsoft ドキュメント"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプレイ Web アプリ |Microsoft ドキュメント"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android アプリ"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "スペース区切りの機能カラー表 - MDN |使用できる"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キーバインドのカスタマイズを許可する |Chromium のバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準準に準プライアンスされない |Chromium のバグ"  
[CR1040019]: https://crbug.com/1040019 "DevTools: [スタイル] ウィンドウで画像と背景画像を簡単にプレビューする |Chromium のバグ"  
[CR1040025]: https://crbug.com/1040025 "DevTools: 要素ポップオーバーに基本的な a11y 情報を表示する |Chromium のバグ"  
[CR1048378]: https://crbug.com/1048378 "ハイ コントラスト モードの DevTools UI のサポート |Chromium のバグ"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium のバグ"  
[CR1068116]: https://crbug.com/1068116 "配送のパネル |Chromium のバグ"  
[CR1072952]: https://crbug.com/1072952 "DevTools: カラー ピッカーが最新の CSS カラー構文を作成する必要があります |Chromium のバグ"  
[CR1075437]: https://crbug.com/1075437 "DevTools: CSS の 'リバート' キーと値のサポートを追加する |Chromium のバグ"  
[CR1076112]: https://crbug.com/1076112 "開発ツールの個人用設定 - 図面のサイズ変更"  
[CR1081486]: https://crbug.com/1081486 "スクリーンキャスト モードのナビゲーション ボタンにキーボード フォーカスが表示されない |Chromium のバグ"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus は 'fulfilled' で、'解決' でない ' にする必要があります |V8 バグ"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "色 3 - CSS カラー モジュール レベル 4 からの変更 |W3C CSS 作業グループ エディターの下書き"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. Foreground Color: 'color' - CSS カラー モジュール レベル 4 |W3C CSS 作業グループ エディターの下書き"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新しい Microsoft Edge のご説明"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "都道府県と Fates - domenic/promises-unwrapping |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "リバート |MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "ブラウザーの互換性 |MDN"  

[VSCode]: https://code.visualstudio.com/ "Visual Studioコード"  
[VSCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Windows のコード ショートカット"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "軸: キーボード |WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "軸: 名前の役割値 |WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "Windows でハイ コントラスト モードをオンまたはオフにする |Windows サポート"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "Twitter アカウント@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge 開発者"  
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
> <span data-ttu-id="1ce6c-299">このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-299">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1ce6c-300">ここには元のページが表示[され](https://developers.google.com/web/updates/2020/05/devtools/index)[、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools \& Lighthouse\) によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-300">The original page is found [here](https://developers.google.com/web/updates/2020/05/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1ce6c-302">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1ce6c-302">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
