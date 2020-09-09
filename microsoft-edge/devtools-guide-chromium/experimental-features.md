---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: c78e9aa5e0b4d808dd67d607a954b185ddcf54e7
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004031"
---
# <span data-ttu-id="b35f4-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="b35f4-104">Experimental features</span></span>  

<span data-ttu-id="b35f4-105">Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="b35f4-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="b35f4-106">各機能がリリースされる前に、テストして、[フィードバックを提供](#providing-feedback-on-experimental-features) することができます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-106">You may test and p[provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="b35f4-107">Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="b35f4-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-108">Turn on experimental features</span></span>  

<span data-ttu-id="b35f4-109">Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-109">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="b35f4-110">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-110">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="b35f4-111">[ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-111">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="b35f4-112">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-112">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="b35f4-113">[ [設定][DevToolsCustomizeSettings] ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="b35f4-114">を選択し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="b35f4-115">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="b35f4-116">[ **設定** ] ウィンドウの左側で、[ **実験** ] セクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.msft.png":::
       <span data-ttu-id="b35f4-118">DevTools の設定での実験の一覧</span><span class="sxs-lookup"><span data-stu-id="b35f4-118">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b35f4-119">[ **実験** ] ページで、利用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b35f4-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="b35f4-120">Microsoft Edge DevTools を閉じてからもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-120">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="b35f4-121">実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b35f4-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="b35f4-122">実験的な機能を無効にするには、[ **実験** ] ページを開き、無効にする実験的機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b35f4-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="b35f4-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="b35f4-123">Highlighted experimental features</span></span>  

<span data-ttu-id="b35f4-124">以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="b35f4-125">実験的機能</span><span class="sxs-lookup"><span data-stu-id="b35f4-125">Experimental feature</span></span> | <span data-ttu-id="b35f4-126">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="b35f4-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="b35f4-127">カスタムキーボードショートカットの [設定] タブを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-127">Enable custom keyboard shortcuts settings tab</span></span>](#enable-custom-keyboard-shortcuts-settings-tab) | <span data-ttu-id="b35f4-128">84以降</span><span class="sxs-lookup"><span data-stu-id="b35f4-128">84 or later</span></span> |
| [<span data-ttu-id="b35f4-129">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="b35f4-129">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="b35f4-130">84以降</span><span class="sxs-lookup"><span data-stu-id="b35f4-130">84 or later</span></span> |  
| [<span data-ttu-id="b35f4-131">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-131">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="b35f4-132">85以降</span><span class="sxs-lookup"><span data-stu-id="b35f4-132">85 or later</span></span> |  
| [<span data-ttu-id="b35f4-133">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-133">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="b35f4-134">85以降</span><span class="sxs-lookup"><span data-stu-id="b35f4-134">85 or later</span></span> |  
| [<span data-ttu-id="b35f4-135">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-135">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="b35f4-136">85以降</span><span class="sxs-lookup"><span data-stu-id="b35f4-136">85 or later</span></span> |  
| [<span data-ttu-id="b35f4-137">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-137">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="b35f4-138">85以降</span><span class="sxs-lookup"><span data-stu-id="b35f4-138">85 or later</span></span> |  
| [<span data-ttu-id="b35f4-139">ソースオーダービューアーを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-139">Enable Source Order Viewer</span></span>](#enable-source-order-viewer) | <span data-ttu-id="b35f4-140">86以降</span><span class="sxs-lookup"><span data-stu-id="b35f4-140">86 or later</span></span> |  

### <span data-ttu-id="b35f4-141">カスタムキーボードショートカットの [設定] タブを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-141">Enable custom keyboard shortcuts settings tab</span></span>  

<span data-ttu-id="b35f4-142">Devtools の [[設定][DevToolsCustomizeSettings]] に新しい [**ショートカット**] ページが用意されており、開発ツールの[キーボードショートカット][DevToolsShortcuts]と[Microsoft Visual Studio のコード][VisualstudioCode]の対応を示しています。</span><span class="sxs-lookup"><span data-stu-id="b35f4-142">Provides a new **Shortcuts** page in [DevTools Settings][DevToolsCustomizeSettings] to match [keyboard shortcuts][DevToolsShortcuts] in the DevTools to [Microsoft Visual Studio Code][VisualstudioCode].</span></span>  

<span data-ttu-id="b35f4-143">実験を有効にした後、[選択] を使用して、[ [Devtools][DevToolsCustomizeSettings] ] の設定をもう一度開き `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-143">After you enable the experiment, open [DevTools Settings][DevToolsCustomizeSettings] again using select `Shift`+`?`.</span></span>  <span data-ttu-id="b35f4-144">[新しい **ショートカット** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-144">Navigate to the new **Shortcuts** page.</span></span>  <span data-ttu-id="b35f4-145">[**標準のショートカットキー**の選択] ドロップダウンで [ **Devtools (既定値)** ] を選び、[ **Visual Studio コード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-145">Select **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="b35f4-146">DevTools のキーボードショートカットは、Visual Studio コードで同等のアクションのショートカットと一致するようになりました。</span><span class="sxs-lookup"><span data-stu-id="b35f4-146">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in Visual Studio Code.</span></span>  

:::image type="complex" source="./media/experiments-keyboard-shortcut.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="./media/experiments-keyboard-shortcut.msft.png":::
   <span data-ttu-id="b35f4-148">DevTools for Visual Studio コードのキーボードショートカットを一致させる</span><span class="sxs-lookup"><span data-stu-id="b35f4-148">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="b35f4-149">たとえば、Windows では、 [Visual Studio コード][VisualstudioCodeShortcutsKeyboardWindows] でスクリプトを一時停止または実行し続けるためのキーボードショートカットは `F5` です。</span><span class="sxs-lookup"><span data-stu-id="b35f4-149">For example, on Windows the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualstudioCodeShortcutsKeyboardWindows] is `F5`.</span></span>  <span data-ttu-id="b35f4-150">**Devtools (既定)** の事前設定を使用すると、devtools の同じショートカットを使うことが `F8` できます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-150">With the **DevTools (Default)** preset, the same shortcut in the DevTools is `F8`.</span></span>  <span data-ttu-id="b35f4-151">**Visual Studio コード**の事前設定を使用すると、ショートカットも表示され `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-151">With the **Visual Studio Code** preset, the shortcut is also `F5`.</span></span>  

### <span data-ttu-id="b35f4-152">エミュレーション: デュアルスクリーンモードのサポート</span><span class="sxs-lookup"><span data-stu-id="b35f4-152">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="b35f4-153">Microsoft Edge で2つの新しいデュアル画面と折りたたみ式デバイスをエミュレートするための追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-153">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="b35f4-154">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="b35f4-154">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="b35f4-155">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="b35f4-155">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  

<span data-ttu-id="b35f4-156">デバイスをエミュレートし、次の後処理を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-156">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="b35f4-157">シングルスクリーンまたは折り目</span><span class="sxs-lookup"><span data-stu-id="b35f4-157">single-screen or folded posture</span></span>  
*   <span data-ttu-id="b35f4-158">デュアルスクリーンまたは折る</span><span class="sxs-lookup"><span data-stu-id="b35f4-158">dual-screen or unfolded posture</span></span>  

<span data-ttu-id="b35f4-159">[ [実験的な api を有効](#enable-experimental-apis) にする] を使って、デバイスの web サイトを拡張します (またはアプリ \)。</span><span class="sxs-lookup"><span data-stu-id="b35f4-159">Use the [enable experimental APIs](#enable-experimental-apis) to enhance your website \(or app\) for a device.</span></span>  <span data-ttu-id="b35f4-160">[CSS メディアクエリと JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-160">You may also use the [CSS media queries and the JavaScript Windows Segment Enumeration API][GitHubMicrosoftedgeMsedgeexplainerFoldables].</span></span>  

<!-- This image was taken in Chromium Canary since we don't yet have an Edge Canary that has Stan's changes -->  

:::image type="complex" source="./media/experiments-dual-screen-emulation.msft.png" alt-text="Microsoft Edge で Surface Duo をエミュレートする" lightbox="./media/experiments-dual-screen-emulation.msft.png":::  
   <span data-ttu-id="b35f4-162">Microsoft Edge で Surface Duo をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="b35f4-162">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="b35f4-163">実験的な Api を有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-163">Enable experimental APIs</span></span>  

<span data-ttu-id="b35f4-164">Microsoft Edge DevTools で [この実験を有効](#turn-on-experimental-features) にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-164">To [enable this experiment](#turn-on-experimental-features) in the Microsoft Edge DevTools, complete the following steps.</span></span>  

1.  <span data-ttu-id="b35f4-165">に移動 `edge://flags` します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-165">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="b35f4-166">[ **検索フラグ** ] ボックスに、「 `Experimental Web Platform features` 実験的な **Web Platform 機能** 」というフラグを選択して、[ **無効** ] を [ **有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-166">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="b35f4-167">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="b35f4-167">Restart Microsoft Edge.</span></span>  

<span data-ttu-id="b35f4-168">デュアルスクリーンおよび折りたたみ式デバイス向けの web サイトやアプリを改善するには、「 [CSS メディアクエリ」と「JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-168">To enhance your website or app for dual-screen and foldable devices, navigate to [CSS media queries and the JavaScript Windows Segment Enumeration API][GitHubMicrosoftedgeMsedgeexplainerFoldables].</span></span>

<span data-ttu-id="b35f4-169">Microsoft Edge DevTools で[この実験をオン](#turn-on-experimental-features)にします。</span><span class="sxs-lookup"><span data-stu-id="b35f4-169">[Turn on this experiment](#turn-on-experimental-features) in the Microsoft Edge DevTools.</span></span>  

1.  <span data-ttu-id="b35f4-170">Microsoft Edge で新しいタブを開き、に移動し `edge://flags` ます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-170">Open a new tab in Microsoft Edge and navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="b35f4-171">**検索フラグ**のテキストボックスで、「 `Experimental Web Platform features` **実験的な Web プラットフォーム機能**」を選択して、[**無効**] を [**有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-171">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose **Experimental Web Platform features**, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="b35f4-172">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="b35f4-172">Restart Microsoft Edge.</span></span>  

<span data-ttu-id="b35f4-173">デュアルスクリーンデバイスと折りたたみ式デバイス向けの web サイトを拡張する方法の詳細については、「 [CSS メディアクエリ」および「JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-173">For more information about enhancing your website \(or app\) for dual-screen and foldable devices, navigate to [CSS media queries and the JavaScript Windows Segment Enumeration API][GitHubMicrosoftedgeMsedgeexplainerFoldables].</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="実験的な Web Platform 機能のフラグを有効にする" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="b35f4-175">実験的な Web Platform 機能のフラグを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-175">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b35f4-176">[CSS メディアクエリまたは JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]を使用して[surface duo][SurfaceDevicesDuo]の web サイトまたはアプリを強化する場合は、 [Surface Duo][SurfaceDevicesDuo]デバイス上の[Android Microsoft Edge アプリ][GooglePlayMicrosoftEdge]の試用版の**Web プラットフォーム機能**フラグも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b35f4-176">If you are using [CSS media queries or the JavaScript Windows Segment Enumeration API][GitHubMicrosoftedgeMsedgeexplainerFoldables] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>
> 
> <span data-ttu-id="b35f4-177">[Microsoft edge][MicrosoftEdge] [アプリの android][GooglePlayMicrosoftEdge]microsoft Edge で**実験的な Web Platform 機能**のフラグが有効になっている場合、デスクトップ microsoft edge の surface duo エミュレーターの web サイトまたはアプリの動作は[surface duo][SurfaceDevicesDuo]の[Android microsoft edge アプリ][GooglePlayMicrosoftEdge]と一致しません。</span><span class="sxs-lookup"><span data-stu-id="b35f4-177">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge will not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="b35f4-178">[デスクトップ Microsoft edge][MicrosoftEdge]で Surface Duo エミュレーターを正常に使用するために、Android とデスクトップの microsoft edge の間でフラグが一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-178">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="b35f4-179">折りたたみ式とデュアルスクリーンデバイスでのテスト</span><span class="sxs-lookup"><span data-stu-id="b35f4-179">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="b35f4-180">Microsoft Edge のデュアル画面で [Surface Duo][SurfaceDevicesDuo] をエミュレートすると、この **継ぎ目** は、web サイトまたはアプリの上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-180">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the **seam** is drawn over your website or app.</span></span>  

> [!NOTE]
> <span data-ttu-id="b35f4-181">**継ぎ目**は、2つの画面間の間隔です。</span><span class="sxs-lookup"><span data-stu-id="b35f4-181">The **seam** is the space between the two screens.</span></span>  

<span data-ttu-id="b35f4-182">Web サイト \ (またはアプリ \) のエミュレートされたディスプレイが正しい表現です。</span><span class="sxs-lookup"><span data-stu-id="b35f4-182">The emulated display for your website \(or app\) is a correct representation.</span></span>  <span data-ttu-id="b35f4-183">[Surface Duo][SurfaceDevicesDuo]の[Microsoft Edge Android アプリ][GooglePlayMicrosoftEdge]の表示と一致します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-183">It matches the display in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="b35f4-184">**継ぎ目**に合わせて表示されるようにコンテンツを更新します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-184">Update the content to display better along the **seam**.</span></span>  <span data-ttu-id="b35f4-185">Web サイトの外観を **seam**に適合させる方法の詳細については、Surface Duo のドキュメントで [seam を操作する方法][DualScreenIntroductionHowWorkSeam] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-185">For more information about adapting your website \(or app\) to the **seam**, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam] in the Surface Duo documentation.</span></span>  

<span data-ttu-id="b35f4-186">[デバイスツールバー][DevtoolsDeviceModeIndexSimulateMobileViewport]には、web サイトまたはアプリを複数の方法でテストするための追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b35f4-186">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="b35f4-187">**Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 \ (回転 \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-187">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="b35f4-188">この機能を **スパン** \ ( ![ スパン \) と組み合わせると、シングル画面で、または折る、または折り目を切り替えることが ][ImageSpanIcon] できます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-188">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="b35f4-189">これらの機能により、web サイトやアプリを4つのすべての方法でテストできます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-189">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="b35f4-191">デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス</span><span class="sxs-lookup"><span data-stu-id="b35f4-191">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="b35f4-192">**実験的な Web platform 機能**\ ( ![ ExperimentalApis ][ImageExperimentalApisIcon] \) アイコンは、**実験的な web プラットフォーム機能**のフラグの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-192">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="b35f4-193">フラグがオンになっている場合は、アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-193">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="b35f4-194">フラグがオフになっている場合、アイコンは強調表示されません。</span><span class="sxs-lookup"><span data-stu-id="b35f4-194">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="b35f4-195">フラグをオンまたはオフにするには、アイコンを選択するか、または `edge://flags` フラグを移動して切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-195">To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.</span></span>  

#### <span data-ttu-id="b35f4-196">その他の資料</span><span class="sxs-lookup"><span data-stu-id="b35f4-196">Additional resources</span></span>  
*   <span data-ttu-id="b35f4-197">開発の詳細については、「 [デュアルスクリーン web エクスペリエンス][DualScreenWebIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-197">For more information about developing, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="b35f4-198">Surface Duo エミュレーターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b35f4-198">Install the Surface Duo emulator].</span></span>  <span data-ttu-id="b35f4-199">これは、Microsoft Edge のエミュレーターとは異なります。</span><span class="sxs-lookup"><span data-stu-id="b35f4-199">It is different from the emulator in Microsoft Edge.</span></span>  <span data-ttu-id="b35f4-200">Android を実行している Surface Duo をエミュレートし、 [Android Studio][AndroidDeveloperStudio]と統合します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-200">It emulates the Surface Duo running Android and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="b35f4-201">詳細については、「 [Surface DUO SDK の入手][DualScreenAndroidGetDuoSdk]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-201">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

### <span data-ttu-id="b35f4-202">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-202">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="b35f4-203">CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-203">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="b35f4-204">DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-204">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.msft.png":::
   <span data-ttu-id="b35f4-206">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="b35f4-206">CSS grid debugging feature</span></span>  
:::image-end:::  

<span data-ttu-id="b35f4-207">最新の実験的な機能をプレビューするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-207">To preview the latest experimental features, complete the following actions.</span></span>  

1.  <span data-ttu-id="b35f4-208">[ **実験** ] セクションで、[ **新しい CSS グリッドのデバッグ機能を有効にする] チェックボックスをオンにします (再起動後に、レイアウトサイドバーウィンドウで使用可能な構成オプション)** 。</span><span class="sxs-lookup"><span data-stu-id="b35f4-208">In the **Experiments** section, choose the **Enable new CSS Grid debugging features (configuration options available in Layout sidebar pane in Elements after restart)** checkbox.</span></span>  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="b35f4-209">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-209">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="b35f4-210">通常、 **要素** や **ネットワーク** などのツールは、devtools の上部にあるメインパネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-210">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="b35f4-211">**3D ビュー**などのツール、および devtools の下部にある**引き出し**パネルで通常のみ開かれる**問題**。</span><span class="sxs-lookup"><span data-stu-id="b35f4-211">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="b35f4-212">実験を選択した後、上下のパネル間でツールを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-212">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="b35f4-213">ツールを移動するには、タブの上にマウスポインターを合わせて、コンテキストメニューの [ **先頭へ移動** ] または [ **下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-213">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="b35f4-214">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-214">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="b35f4-215">**ドロワー**パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-215">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.msft.png":::
   <span data-ttu-id="b35f4-217">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="b35f4-217">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="b35f4-218">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-218">Enable webhint</span></span>  

<span data-ttu-id="b35f4-219">[webhint][WebhintMain] は、web サイトやローカル web ページにリアルタイムでフィードバックを提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="b35f4-219">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="b35f4-220">[Webhint][WebhintMain]によって提供されるフィードバックの種類。</span><span class="sxs-lookup"><span data-stu-id="b35f4-220">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="b35f4-221">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="b35f4-221">accessibility</span></span>  
*   <span data-ttu-id="b35f4-222">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="b35f4-222">cross-browser compatibility</span></span>  
*   <span data-ttu-id="b35f4-223">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="b35f4-223">security</span></span>  
*   <span data-ttu-id="b35f4-224">処理</span><span class="sxs-lookup"><span data-stu-id="b35f4-224">performance</span></span>  
*   <span data-ttu-id="b35f4-225">PWA</span><span class="sxs-lookup"><span data-stu-id="b35f4-225">PWAs</span></span>  
*   <span data-ttu-id="b35f4-226">その他の一般的な web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="b35f4-226">other common web development issues</span></span>  

<span data-ttu-id="b35f4-227">[Webhint][WebhintMain]の実験では、[[問題][DevtoolsIssues]] パネルに webhint のフィードバックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-227">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="b35f4-228">問題を選択すると、ソリューションのドキュメントと web サイト上の影響を受けるリソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-228">Select an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="b35f4-229">リソースリンクを選んで、DevTools で関連する **ネットワーク**、 **ソース**、または **要素** のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-229">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.msft.png":::
   <span data-ttu-id="b35f4-231">[ **問題** ] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="b35f4-231">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="b35f4-232">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-232">Enable Network Console</span></span>  

<span data-ttu-id="b35f4-233">**ネットワーク本体** は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="b35f4-233">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="b35f4-234">**ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-234">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="b35f4-235">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-235">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="b35f4-236">**ネットワークコンソール**を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-236">To use the **Network Console**, use the following steps.</span></span>    

1.  <span data-ttu-id="b35f4-237">[ **ネットワーク** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-237">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="b35f4-238">変更して再送信するネットワーク要求を見つけます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-238">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="b35f4-239">コンテキストメニューを開き (\ 右クリック \)、[ **編集と再生**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-239">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="b35f4-240">**ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-240">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="b35f4-241">[ **送信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-241">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="Console ドローワのネットワーク本体" lightbox="./media/network-network-console.msft.png":::
   <span data-ttu-id="b35f4-243">**Console**ドローワの**ネットワーク本体**</span><span class="sxs-lookup"><span data-stu-id="b35f4-243">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="b35f4-244">ソースオーダービューアーを有効にする</span><span class="sxs-lookup"><span data-stu-id="b35f4-244">Enable Source Order Viewer</span></span>  

<span data-ttu-id="b35f4-245">**ソースオーダービューアー** は、ページソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="b35f4-245">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="b35f4-246">オンスクリーン表示の順序は、ソースの順序とは異なる場合があります。これには、スクリーンリーダーとキーボードのユーザーが混乱させるます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-246">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="b35f4-247">**ソース注文ビューアー**を使用して、画面上の表示順序とソースの順序の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-247">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="b35f4-248">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="b35f4-248">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="b35f4-249">ソースオーダービューアーを使用するには:</span><span class="sxs-lookup"><span data-stu-id="b35f4-249">To use Source Order Viewer:</span></span>  

1.  <span data-ttu-id="b35f4-250">[ **要素** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="b35f4-250">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="b35f4-251">[引き出し] \ (下) パネルで [ **アクセシビリティ** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b35f4-251">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="b35f4-252">[ **ソース注文のビューアー** ] セクションで、[ **ソースの順序を表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b35f4-252">Under the **Source Order Viewer** section, select the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="b35f4-253">任意の HTML 要素を強調表示して、ページソースの順序でオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-253">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソースオーダービューアー" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="b35f4-255">[**アクセシビリティ**] ウィンドウの**ソースオーダービューアー**</span><span class="sxs-lookup"><span data-stu-id="b35f4-255">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## <span data-ttu-id="b35f4-256">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="b35f4-256">Previous experimental features</span></span>  

*   <span data-ttu-id="b35f4-257">Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="b35f4-257">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  

## <span data-ttu-id="b35f4-258">実験的な機能についてフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="b35f4-258">Providing feedback on experimental features</span></span>  

<span data-ttu-id="b35f4-259">Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="b35f4-259">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="b35f4-260">DevTools のフィードバックの **送信** アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="b35f4-260">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="b35f4-261">[@EdgeDevTools][TwitterEdgedevtools]ツイート</span><span class="sxs-lookup"><span data-stu-id="b35f4-261">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="b35f4-263">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="b35f4-263">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
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

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン web エクスペリエンス |Microsoft ドキュメント"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo エミュレーターの入手 |Microsoft ドキュメント"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "Seam の操作方法-デュアルスクリーンデバイスの概要 |Microsoft ドキュメント"  

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[VisualstudioCode]: https://code.visualstudio.com "Microsoft Visual Studio コード"  
[VisualstudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio のコードのキーボードショートカット (Windows |) |Microsoft Visual Studio コード"  

[GitHubMicrosoftedgeMsedgeexplainerFoldables]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ式デバイスでの対応エクスペリエンスのための Web プラットフォームプリミティブGitHub"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy 折りたたみ |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "web ヒント"  
