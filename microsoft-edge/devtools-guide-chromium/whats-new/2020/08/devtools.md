---
description: キーボード ショートカットを Visual Studio Code と一致させる、Surface Duo と Samsung Galaxy Fold をエミュレートする、CSS グリッドのオーバーレイの機能強化など。
title: DevTools の新機能 (Microsoft Edge 86)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0e759c18b5ef547bfd490f4d525930f92809a6a1
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "11133912"
---
# <span data-ttu-id="3cc1d-104">DevTools の新機能 (Microsoft Edge 86)</span><span class="sxs-lookup"><span data-stu-id="3cc1d-104">What's New In DevTools (Microsoft Edge 86)</span></span>  

## <span data-ttu-id="3cc1d-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="3cc1d-105">Announcements from the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### <span data-ttu-id="3cc1d-106">DevTools のキーボード ショートカットを Visual Studio Code と一致させる</span><span class="sxs-lookup"><span data-stu-id="3cc1d-106">Match keyboard shortcuts in DevTools to Visual Studio Code</span></span>  

<span data-ttu-id="3cc1d-107">Microsoft Edge 86 では、DevTools のキーボード ショートカットを [Visual Studio Code][VisualStudioCode] のショートカットと一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-107">In Microsoft Edge 86, you may match keyboard shortcuts in the DevTools to your shortcuts in [Visual Studio Code][VisualStudioCode].</span></span> 

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="DevTools のキーボード ショートカットを Visual Studio Code と一致させる" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   <span data-ttu-id="3cc1d-109">DevTools のキーボード ショートカットを Visual Studio Code と一致させる</span><span class="sxs-lookup"><span data-stu-id="3cc1d-109">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-110">この機能を有効にするには、「[Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする][DevtoolsCustomizeShortcuts]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-110">To activate this feature, navigate to [Customize keyboard shortcuts in the Microsoft Edge DevTools][DevtoolsCustomizeShortcuts].</span></span>  

<span data-ttu-id="3cc1d-111">たとえば、[Visual Studio Code][VisualStudioCodeShortcutsKeyboardWindows] でスクリプトを一時停止または実行し続けるためのキーボード ショートカットは `F5` です。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-111">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualStudioCodeShortcutsKeyboardWindows] is `F5`.</span></span>  <span data-ttu-id="3cc1d-112">**DevTools (既定)** の事前設定では、DevTools での同じショートカットは `F8` ですが、**Visual Studio Code** の事前設定を選ぶと、`F5` も同じショートカットとして利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-112">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8`, but when you choose the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="3cc1d-113">Chromium の問題 [#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-113">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="3cc1d-114">Surface Duo と Samsung Galaxy Fold のエミュレート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-114">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="3cc1d-116">試験的機能</span><span class="sxs-lookup"><span data-stu-id="3cc1d-116">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-117">Microsoft Edge を使用して、[Surface Duo][MicrosoftSurfaceDevicesDuo] と [Samsung Galaxy Fold][SamsungMobileGalaxyFold] の 2 つの新しいデバイスでの Web サイトまたはアプリの外観をテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-117">You are now able to test the look and feel of your website or app on two new devices:  [Surface Duo][MicrosoftSurfaceDevicesDuo] and [Samsung Galaxy Fold][SamsungMobileGalaxyFold] in Microsoft Edge.</span></span>  

<span data-ttu-id="3cc1d-118">デュアルスクリーン デバイスと折りたたみ式デバイスのために Web サイトやアプリを強化するには、[デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-118">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="3cc1d-119">[スパニング][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: Web サイト (またはアプリ) が両方の画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-119">[Spanning][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>
*   <span data-ttu-id="3cc1d-120">[シームのレンダリング][DualScreenIntroductionHowWorkSeam]: シームとは、2 つの画面の間の領域のことです。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-120">[Rendering the seam][DualScreenIntroductionHowWorkSeam], which is the space between the two screens.</span></span>
*   <span data-ttu-id="3cc1d-121">[試験的な Web プラットフォーム API を有効にして][DevtoolsExperimentalFeaturesEnableExperimentalApis]、新しい [CSS メディア画面スパニング機能][DualScreenWebCssMediaSpanning]と [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments] にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-121">[Enabling experimental Web Platform APIs][DevtoolsExperimentalFeaturesEnableExperimentalApis] to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments].</span></span>  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="Surface Duo のデバイス エミュレーション" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   <span data-ttu-id="3cc1d-123">Surface Duo のデバイス エミュレーション</span><span class="sxs-lookup"><span data-stu-id="3cc1d-123">Device emulation for Surface Duo</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-124">この試験的機能を有効にするには、「[実験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]」に移動し、[**エミュレーション: デュアル スクリーン モードのサポート**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-124">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Emulation: Support dual screen mode**.</span></span>  

<span data-ttu-id="3cc1d-125">この実験の詳細については、「[エミュレーション: デュアル スクリーン モードのサポート][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-125">For more information about this experiment, navigate to [Emulation: Support dual screen mode][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode].</span></span>  

<span data-ttu-id="3cc1d-126">Chromium の問題: [#1054281][CR1054281]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-126">Chromium issue: [#1054281][CR1054281]</span></span>  

### <span data-ttu-id="3cc1d-127">CSS グリッドのオーバーレイの機能強化と新しい試験的なグリッド機能</span><span class="sxs-lookup"><span data-stu-id="3cc1d-127">CSS grid overlay improvements and new experimental grid features</span></span>  

<span data-ttu-id="3cc1d-128">CSS グリッドのオーバーレイの機能強化について、積極的なご意見をお寄せいただきありがとうございました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-128">Thank you for the positive feedback about the improved CSS grid overlays.</span></span>  <span data-ttu-id="3cc1d-129">CSS グリッドのオーバーレイは既定で有効になりましたので、実験を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-129">The CSS grid overlays are now enabled by default and do not require you to turn on an experiment.</span></span>  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="article 要素の CSS グリッドのオーバーレイ" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   <span data-ttu-id="3cc1d-131">`article` 要素の CSS グリッドのオーバーレイ</span><span class="sxs-lookup"><span data-stu-id="3cc1d-131">CSS grid overlay for `article` element</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="3cc1d-132">グリッドのオーバーレイの詳細については、「[CSS グリッドのデバッグ機能][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-132">For more information about grid overlays, go to [CSS grid debugging features][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="3cc1d-133">Microsoft Edge DevTools チームと Chrome DevTools チームは、追加機能のための共同作業を行っています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-133">The Microsoft Edge DevTools team and the Chrome DevTools team collaborate on additional features.</span></span>  <span data-ttu-id="3cc1d-134">新機能には、[**要素**] パネルにある新しい [**レイアウト**] ウィンドウで構成可能な、永続的な複数のオーバーレイが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-134">The new features include multiple overlays that are persistent and configurable from a new **Layout** pane on the **Elements** panel.</span></span>  

<span data-ttu-id="3cc1d-135">この試験的機能を有効にするには、「[実験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]」に移動し、[**新しい CSS グリッドのデバッグ機能を有効にする (再起動後、[要素] にある [レイアウト] サイド バーウィンドウで構成オプションを利用できます)**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-135">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable new CSS Grid debugging features (configuration options available in Layout sidebar pane in Elements after restart)**.</span></span>  

<span data-ttu-id="3cc1d-136">この実験の詳細については、「[新しい CSS グリッドのデバッグ機能を有効にする][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-136">For more information about this experiment, navigate to [Enable new CSS grid debugging features][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="3cc1d-137">Chromium の問題: [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-137">Chromium issue: [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="3cc1d-138">コンソールからコピーした表の書式の保持</span><span class="sxs-lookup"><span data-stu-id="3cc1d-138">Table copied from the Console preserves formatting</span></span>  

<span data-ttu-id="3cc1d-139">Microsoft Edge 85 以前のバージョンでは、コピーした `console.table` の書式設定が失われていました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-139">In Microsoft Edge 85 or earlier, the formatting of a copied `console.table` was lost.</span></span>  <span data-ttu-id="3cc1d-140">[table][DevtoolsConsoleApiTable] コンソール API から出力をコピーして貼り付けた場合、表のテキストのみが保持されました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-140">If you copied the output from the [table][DevtoolsConsoleApiTable] Console API, and pasted it, only the text of the table was kept.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="Microsoft Edge 85 以前の table コンソール API の出力" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` <span data-ttu-id="3cc1d-142">Microsoft Edge 85 以前のコンソール API の出力</span><span class="sxs-lookup"><span data-stu-id="3cc1d-142">Console API output in Microsoft Edge 85 or earlier</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 85 以前のバージョンから Visual Studio Code に貼り付けられた table コンソール API" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="3cc1d-144">Microsoft Edge 85 以前のバージョンから Visual Studio Code に貼り付けられたコンソール API</span><span class="sxs-lookup"><span data-stu-id="3cc1d-144">Console API output from Microsoft Edge 85 or earlier pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3cc1d-145">Microsoft Edge 86 以降のバージョンでは、**コンソール**から表をコピーすると、書式設定が保持されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-145">In Microsoft Edge 86 or later, when you copy a table from the **Console**, the formatting is now preserved.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="Microsoft Edge 86 以降の table コンソール API の出力" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` <span data-ttu-id="3cc1d-147">Microsoft Edge 86 以降のコンソール API の出力</span><span class="sxs-lookup"><span data-stu-id="3cc1d-147">Console API output in Microsoft Edge 86 or later</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 86 以降のバージョンから Visual Studio Code に貼り付けられた table コンソール API" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="3cc1d-149">Microsoft Edge 86 以降のバージョンから Visual Studio Code に貼り付けられたコンソール API</span><span class="sxs-lookup"><span data-stu-id="3cc1d-149">Console API output from Microsoft Edge 86 or later pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3cc1d-150">Chromium の問題: [#1115011][CR1115011]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-150">Chromium issue: [#1115011][CR1115011]</span></span>  

### <span data-ttu-id="3cc1d-151">アクセシビリティ テストをより簡単にするためのソース オーダー ビューアー</span><span class="sxs-lookup"><span data-stu-id="3cc1d-151">Source Order Viewer for easier accessibility testing</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="3cc1d-153">試験的機能</span><span class="sxs-lookup"><span data-stu-id="3cc1d-153">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-154">新しくなったアクセシビリティ ヘルパーでは、ソース内の要素の順序を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-154">The new accessibility helper displays the order of elements in the source.</span></span>  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="ソースの順序の表示を有効にする" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   <span data-ttu-id="3cc1d-156">**ソースの順序の表示**を有効にする</span><span class="sxs-lookup"><span data-stu-id="3cc1d-156">Activate **Show source order**</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-157">この機能により、スクリーン リーダーとキーボード ユーザーの Web サイトまたはアプリ エクスペリエンスをより簡単にテストできます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-157">This feature makes it easier to test the way screen reader and keyboard users experience your website or app.</span></span>  <span data-ttu-id="3cc1d-158">スクリーン リーダーとキーボード ナビゲーションは、コンテンツが Web サイトまたはアプリのソース コードと同じ順序で配置され、レンダリングするページと一致しているかどうかに依存しています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-158">Screen readers and keyboard navigation depend on content being placed in a particular order in the source code of your website or app, so that it matches the rendered page.</span></span>  <span data-ttu-id="3cc1d-159">ソース オーダー ビューアーは、レンダリングされたページとソース コードの順序の潜在的な相違点を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-159">The Source Order Viewer displays potential differences in order between the rendered page and the source code.</span></span>  

<span data-ttu-id="3cc1d-160">この試験的機能を有効にするには、「[試験的機能を有効にする][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]」に移動し、[**ソース オーダー ビューアーを有効にする**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-160">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Source Order Viewer**.</span></span>  

<span data-ttu-id="3cc1d-161">この実験の詳細については、「[ソース オーダー ビューアーを有効にする][DevtoolsExperimentalFeaturesEnableSourceOrderViewer]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-161">For more information about this experiment, navigate to [Enable Source Order Viewer][DevtoolsExperimentalFeaturesEnableSourceOrderViewer].</span></span>  

<span data-ttu-id="3cc1d-162">Chromium の問題: [#1094406][CR1094406]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-162">Chromium issue: [#1094406][CR1094406]</span></span>  

<!--
### DevTools language enhancements  

Your feedback and internal discoveries uncovered which text strings used in the Microsoft Edge feedback should remain untranslated or create confusion when translated.  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-stable.msft.png" alt-text="Microsoft Edge DevTools in Traditional Chinese" lightbox="localization-improvements-chinese-complex-stable.msft.png":::
         Microsoft Edge DevTools 85 and earlier in Traditional Chinese  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png" alt-text="Microsoft Edge DevTools in Japanese" lightbox="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png":::
         Microsoft Edge DevTools 86  or later in Traditional Chinese  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.  

The current effort to improve translation quality enables easier support for more languages in the future.  
-->  

### <span data-ttu-id="3cc1d-163">[要素] ツールですべての検索結果を強調表示する</span><span class="sxs-lookup"><span data-stu-id="3cc1d-163">Highlight all search results in Elements tool</span></span>  

<span data-ttu-id="3cc1d-164">Microsoft Edge 84 および 85 では、[**要素**] パネルの最初の検索結果は強調表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-164">In Microsoft Edge 84 and 85, the first search result in the **Elements** panel did not highlight.</span></span>  <span data-ttu-id="3cc1d-165">残りの検索結果だけが正しく強調表示されました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-165">The remaining search results were highlighted correctly.</span></span>  

<span data-ttu-id="3cc1d-166">フィードバックにより Chromium の改善にご協力いただき、ありがとうございました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-166">Thank you for sending your feedback and helping improve Chromium.</span></span>  <span data-ttu-id="3cc1d-167">フィードバックにより、オープン ソースの Chromium プロジェクトの問題 [#1103316][CR1103316] が発見されました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-167">Your feedback uncovered Issue [#1103316][CR1103316] in the open-source Chromium project.</span></span>  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="Microsoft Edge 84 以降のバージョンで [要素] パネルで最初の検索結果が強調表示されている" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   <span data-ttu-id="3cc1d-169">Microsoft Edge 84 以降のバージョンで [**要素**] パネルで最初の検索結果が強調表示されている</span><span class="sxs-lookup"><span data-stu-id="3cc1d-169">Highlighted first search result on **Elements** panel in Microsoft Edge 84 or later</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-170">この問題は、Microsoft Edge のすべてのバージョンで修正されました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-170">The issue is now fixed in all versions of Microsoft Edge.</span></span>  

<span data-ttu-id="3cc1d-171">Chromium の問題: [#1103316][CR1103316]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-171">Chromium issue: [#1103316][CR1103316]</span></span>  

## <span data-ttu-id="3cc1d-172">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="3cc1d-172">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="3cc1d-173">新しい [メディア] パネル</span><span class="sxs-lookup"><span data-stu-id="3cc1d-173">New Media panel</span></span>  

<span data-ttu-id="3cc1d-174">DevTools の [[メディア][DevtoolsMediaPanelIndex]] パネルで、メディア プレーヤーの情報が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-174">DevTools now displays media players information in the [Media][DevtoolsMediaPanelIndex] panel.</span></span>  

<span data-ttu-id="3cc1d-175">新しい [**メディア**] パネルを開くには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-175">To open the new **Media** panel, complete the following step.</span></span>  

1.  <span data-ttu-id="3cc1d-176">[**DevTools のカスタマイズとコントロール**] \(`...`\) > [**その他のツール**] > [**メディア**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-176">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="新しい [メディア] パネル" lightbox="../../media/2020/08/media-panel.msft.png":::
       <span data-ttu-id="3cc1d-178">新しい [**メディア**] パネル</span><span class="sxs-lookup"><span data-stu-id="3cc1d-178">New **Media** panel</span></span>  
    :::image-end:::  

<span data-ttu-id="3cc1d-179">DevTools の新しい [**メディア**] パネルが導入される前、ビデオ プレイヤーに関するログ情報とデバッグ情報は [**最近のプレイヤー**] 設定の下にありました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-179">Before the new **Media** panel in DevTools, the logging and debug information about video players was located under the **Recent Players** setting.</span></span>  <span data-ttu-id="3cc1d-180">[**最近のプレイヤー**] 設定を開くには、`edge://media-internals` に移動して [**プレイヤー**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-180">To open the **Recent Players** setting, go to `edge://media-internals` and choose the **Players** tab.</span></span>  

<span data-ttu-id="3cc1d-181">ライブ コンテンツを表示して、次の例を含む潜在的な問題をより迅速に検査します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-181">View live content and inspect potential issues more quickly, including the following examples.</span></span>  

*   <span data-ttu-id="3cc1d-182">フレームが破棄される原因。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-182">Why frames are dropped?</span></span>  
*   <span data-ttu-id="3cc1d-183">JavaScript が予期しない方法でプレーヤーと対話している原因。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-183">Why JavaScript is interacting with the player in an unexpected way?</span></span>  

### <span data-ttu-id="3cc1d-184">[要素] パネルのコンテキスト メニューを使用したノードのスクリーンショットのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="3cc1d-184">Capture node screenshots using the Elements panel context menu</span></span>  

<span data-ttu-id="3cc1d-185">[**要素**] パネルにあるコンテキスト メニューを使用して、ノードのスクリーンショットをキャプチャできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-185">You may now capture node screenshots using the context menu in the **Elements** panel.</span></span>  

<span data-ttu-id="3cc1d-186">たとえば、目次のスクリーンショットを撮るには、要素にカーソルを合わせてコンテキスト メニューを開き (右クリック)、[**ノードのスクリーンショットをキャプチャ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-186">For example, to take a screenshot of the table of contents, hover on the element, open the contextual menu \(right-click\), and select **Capture node screenshot**.</span></span>  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="ノードのスクリーンショットのキャプチャ" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   <span data-ttu-id="3cc1d-188">ノードのスクリーンショットのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="3cc1d-188">Capture node screenshots</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-189">Chromium の問題: [#1100253][CR1100253]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-189">Chromium issue: [#1100253][CR1100253]</span></span>  

### <span data-ttu-id="3cc1d-190">[問題] ツールの更新</span><span class="sxs-lookup"><span data-stu-id="3cc1d-190">Issues tool updates</span></span>  

<span data-ttu-id="3cc1d-191">**コンソール** パネルの [問題] 警告バーは、通常のメッセージに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-191">The Issues warning bar on the **Console** panel is now replaced with a regular message.</span></span>  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text=""コンソール内の問題" メッセージ" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   <span data-ttu-id="3cc1d-193">"コンソール内の問題" メッセージ</span><span class="sxs-lookup"><span data-stu-id="3cc1d-193">Issues in console message</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-194">サードパーティの Cookie の問題は、[**問題**] ツールで既定で非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-194">Third-party cookie issues are now hidden by default in the **Issues** tool.</span></span>  <span data-ttu-id="3cc1d-195">新しい [**サードパーティの Cookie の問題を含める**] チェックボックスをオンにして、問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-195">Enable the new **Include third-party cookie issues** checkbox to view the issues.</span></span>  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="サードパーティの Cookie の問題チェックボックス" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   <span data-ttu-id="3cc1d-197">サードパーティの Cookie の問題チェックボックス</span><span class="sxs-lookup"><span data-stu-id="3cc1d-197">third-party cookie issues checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-198">Chromium の問題: [1096481][CR1096481]、[1068116][CR1068116]、[1080589][CR1080589]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-198">Chromium issues: [1096481][CR1096481], [1068116][CR1068116], [1080589][CR1080589]</span></span>  

### <span data-ttu-id="3cc1d-199">見つからないローカル フォントのエミュレート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-199">Emulate missing local fonts</span></span>  

<span data-ttu-id="3cc1d-200">[[レンダリング ツール][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]] を開いて、新しい [**ローカル フォントを無効にする**] 機能を使用して `@font-face` 規則の見つからない `local()` ソースをエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-200">Open the [Rendering tool][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] and use the new **Disable local fonts** feature to emulate missing `local()` sources in `@font-face` rules.</span></span>  

<span data-ttu-id="3cc1d-201">たとえば、お使いのデバイスに `Rubik` フォントがインストールされていて、`@font-face src` ルールによって `local()` フォントとして使用されている場合、Microsoft Edge は、お使いのデバイスのローカル フォント ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-201">For example, when the `Rubik` font is installed on your device and the `@font-face src` rule uses it as a `local()` font, Microsoft Edge uses the local font file from your device.</span></span>  

<span data-ttu-id="3cc1d-202">[**ローカル フォントを無効にする**] が有効になっている場合、DevTools は `local()` フォントを無視し、それぞれのフォントをネットワークから取得します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-202">When **Disable local fonts** is enabled, DevTools ignores the `local()` fonts and fetches each from the network.</span></span>  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="見つからないローカル フォントのエミュレート" lightbox="../../media/2020/08/disable-font.msft.png":::
   <span data-ttu-id="3cc1d-204">見つからないローカル フォントのエミュレート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-204">Emulate missing local fonts</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-205">次の例のように、開発中に同じフォントの異なる 2 つのコピーを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="3cc1d-205">If you use two different copies of the same font during development, such as the following examples.</span></span>  

*   <span data-ttu-id="3cc1d-206">デザイン ツールにローカル フォントを使用する。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-206">A local font for your design tools.</span></span>  
*   <span data-ttu-id="3cc1d-207">コードに Web フォントを使用する。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-207">A web font for your code.</span></span>  

<span data-ttu-id="3cc1d-208">[**ローカル フォントを無効にする**] を使用して、次の作業をより簡単に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-208">Use **Disable local fonts** to make it easier for you to complete the following tasks.</span></span>  

*   <span data-ttu-id="3cc1d-209">読み込みのパフォーマンスと Web フォントの最適化をデバッグし、計測する。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-209">Debug and measure loading performance and optimization of web fonts.</span></span>  
*   <span data-ttu-id="3cc1d-210">CSS `@font-face` ルールの精度を検証する。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-210">Verify accuracy of your CSS `@font-face` rules.</span></span>  
*   <span data-ttu-id="3cc1d-211">デバイスにインストールされているローカル バージョンと Web フォントの違いを見つける。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-211">Discover differences between local versions installed on your device and a web font.</span></span>  

<span data-ttu-id="3cc1d-212">Chromium の問題: [#384968][CR384968]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-212">Chromium issue: [#384968][CR384968]</span></span>  

### <span data-ttu-id="3cc1d-213">非アクティブなユーザーのエミュレート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-213">Emulate inactive users</span></span>  

<span data-ttu-id="3cc1d-214">[アイドル検出 API][WebDevIdleDetection] によって、開発者は非アクティブなユーザーを検出し、アイドル状態の変更を反映することができます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-214">The [Idle Detection API][WebDevIdleDetection] allows developers to detect inactive users and react on idle state changes.</span></span>  <span data-ttu-id="3cc1d-215">DevTools を使って、[**センサー**] ツールでユーザーの状態と画面の状態の両方に対してアイドル状態の変更をエミュレートできるようになりました。これにより、実際のアイドル状態が変更されるのを待つ必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-215">You are now able to use DevTools to emulate idle state changes in the **Sensors** tool for both the user state and the screen state instead of waiting for the actual idle state to change.</span></span>  <span data-ttu-id="3cc1d-216">[**センサー**] ツールは [[ドロワー][DevtoolsCustomizeIndexDrawer]] から開くことができます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-216">You may open the **Sensors** tool from the [Drawer][DevtoolsCustomizeIndexDrawer].</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="非アクティブなユーザーのエミュレート" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   <span data-ttu-id="3cc1d-218">非アクティブなユーザーのエミュレート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-218">Emulate inactive users</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-219">Chromium の問題: [#1090802][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-219">Chromium issue: [#1090802][CR1090802]</span></span>  

### <span data-ttu-id="3cc1d-220">prefers-reduced-data のエミュレート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-220">Emulate prefers-reduced-data</span></span>  

> [!NOTE]
> <span data-ttu-id="3cc1d-221">Microsoft Edge 86 でこの機能を有効にするには、`edge://flags#enable-experimental-web-platform-features` に移動し、[**Experimental Web Platform 機能**] フラグをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-221">In Microsoft Edge 86, to enable this feature, go to `edge://flags#enable-experimental-web-platform-features` and turn on the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="3cc1d-222">エミュレーション オプションは、フラグが有効になっている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-222">The emulation option is only displayed if the flag is enabled.</span></span>  

<span data-ttu-id="3cc1d-223">[prefers-reduced-data][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] メディア クエリは、データを最少化するユーザーのコンテンツ設定を検出します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-223">The [prefers-reduced-data][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] media query detects user content preferences for reduced data.</span></span>  <span data-ttu-id="3cc1d-224">これが選択されている場合、ユーザーはより少ないデータを使用する代替のページ コンテンツを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-224">If selected, the user receives alternate page content that uses less data.</span></span>  

<span data-ttu-id="3cc1d-225">DevTools を使って `prefers-reduced-data` メディア クエリをエミュレートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-225">You may now use DevTools to emulate the `prefers-reduced-data` media query.</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="prefers-reduced-data のエミュレート" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   <span data-ttu-id="3cc1d-227">prefers-reduced-data のエミュレート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-227">Emulate prefers-reduced-data</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-228">Chromium の問題: [#1096068][CR1096068]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-228">Chromium issue: [#1096068][CR1096068]</span></span>  

### <span data-ttu-id="3cc1d-229">新しい JavaScript 機能のサポート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-229">Support for new JavaScript features</span></span>  

<span data-ttu-id="3cc1d-230">DevTools では、次の JavaScript 言語機能がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-230">DevTools now have better supported the following JavaScript language features.</span></span>  

| <span data-ttu-id="3cc1d-231">JavaScript 言語機能</span><span class="sxs-lookup"><span data-stu-id="3cc1d-231">JavaScript language feature</span></span> | <span data-ttu-id="3cc1d-232">詳細</span><span class="sxs-lookup"><span data-stu-id="3cc1d-232">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="3cc1d-233">論理代入演算子</span><span class="sxs-lookup"><span data-stu-id="3cc1d-233">Logical assignment operators</span></span>][V8FeaturesLogicalAssignment] | <span data-ttu-id="3cc1d-234">DevTools の [**コンソール**] パネルと [**ソース**] パネルで、`&&=`、`||=`、`??=` の新しい演算子による論理代入がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-234">DevTools now supports logical assignment with the new `&&=`, `||=`, and `??=` operators in the **Console** and **Sources** panels.</span></span>  |  
| <span data-ttu-id="3cc1d-235">[数値区切り記号][V8FeaturesNumericSeparators]の整形出力</span><span class="sxs-lookup"><span data-stu-id="3cc1d-235">Pretty-print [numeric separators][V8FeaturesNumericSeparators]</span></span> | <span data-ttu-id="3cc1d-236">DevTools の [**ソース**] パネルで、数値区切り記号が整形出力されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-236">DevTools now properly pretty-prints the numeric separators in the **Sources** panel.</span></span>  |  

<span data-ttu-id="3cc1d-237">Chromium の問題: [1086817][CR1086817]、[1080569][CR1080569]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-237">Chromium issues: [1086817][CR1086817], [1080569][CR1080569]</span></span>  

### <span data-ttu-id="3cc1d-238">Lighthouse パネルの Lighthouse 6.2</span><span class="sxs-lookup"><span data-stu-id="3cc1d-238">Lighthouse 6.2 in the Lighthouse panel</span></span>  

<span data-ttu-id="3cc1d-239">[**Lighthouse**] パネルで Lighthouse 6.2 が実行されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-239">The **Lighthouse** panel is now running Lighthouse 6.2.</span></span>  <span data-ttu-id="3cc1d-240">すべての変更の一覧については、「[Lighthouse のリリース ノート][GithubGooglechromeLighthouseV620]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-240">For a full list of changes, go to the [Lighthouse release notes][GithubGooglechromeLighthouseV620].</span></span>  

<span data-ttu-id="3cc1d-241">Chromium の問題: [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-241">Chromium issue: [#772558][CR772558]</span></span>  

### <span data-ttu-id="3cc1d-242">[サービス ワーカー] ウィンドウにおける他のオリジン一覧の廃止</span><span class="sxs-lookup"><span data-stu-id="3cc1d-242">Deprecation of other origins listing in the Service Workers pane</span></span>  

<span data-ttu-id="3cc1d-243">DevTools では、[**サービス ワーカー**] ウィンドウ ([**アプリケーション**] パネル > [**サービス ワーカー**] ウィンドウ) で、他のオリジンからのサービス ワーカーの完全な一覧を表示するリンクが提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-243">DevTools now provides a link from the **Service workers** pane \(**Application** panel > **Service workers** pane\) to view the full list of service workers from other origins.</span></span>  <span data-ttu-id="3cc1d-244">DevTools を開かずにリストにアクセスするには、`edge://service-worker-internals/?devtools` に移動します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-244">To access the list without opening the DevTools, go to `edge://service-worker-internals/?devtools`.</span></span>  

<span data-ttu-id="3cc1d-245">以前の DevTools では、[**アプリケーション**] パネル > [**サービス ワーカー**] ウィンドウの下に入れ子になっているリストを表示していました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-245">Previously DevTools displayed a list nested under the **Application** panel > **Service workers** pane.</span></span>  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="他のオリジンへのリンク" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   <span data-ttu-id="3cc1d-247">他のオリジンへのリンク</span><span class="sxs-lookup"><span data-stu-id="3cc1d-247">Link to other origins</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-248">Chromium の問題: [#807440][CR807440]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-248">Chromium issue: [#807440][CR807440]</span></span>  

### <span data-ttu-id="3cc1d-249">フィルター処理されたアイテムのカバレッジの概要を表示する</span><span class="sxs-lookup"><span data-stu-id="3cc1d-249">Show coverage summary for filtered items</span></span>  

<span data-ttu-id="3cc1d-250">DevTools は、カバレッジ情報を再計算し、概要を動的に表示するようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-250">DevTools now recalculate and display a summary of coverage information dynamically.</span></span>  <span data-ttu-id="3cc1d-251">動的表示は、[[カバレッジ][DevtoolsCoverageIndex]] ツールでフィルターが適用されたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-251">The dynamic display is triggered when filters are applied in the [Coverage][DevtoolsCoverageIndex] tool.</span></span>  <span data-ttu-id="3cc1d-252">以前、[**カバレッジ**] ツールでは、常にすべてのカバレッジ情報の概要が表示されていました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-252">Before the **Coverage** tool always displayed a summary of all coverage information.</span></span>  

<span data-ttu-id="3cc1d-253">次の図のうちの最初の図で、初めは概要に `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` と表示されていますが、次の図のうちの 2 番目の図では CSS フィルターが適用され、概要に `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` と表示されています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-253">In the first of the following figures, the summary initially displays `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` and in the second of the following figures, the summary displays `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` after CSS filtering is applied.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="カバレッジの概要" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         <span data-ttu-id="3cc1d-255">カバレッジの概要</span><span class="sxs-lookup"><span data-stu-id="3cc1d-255">Coverage summary</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="フィルター処理されたアイテムのカバレッジの概要" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         <span data-ttu-id="3cc1d-257">フィルター処理されたアイテムのカバレッジの概要</span><span class="sxs-lookup"><span data-stu-id="3cc1d-257">Coverage summary for filtered items</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="3cc1d-258">Chromium の問題: [#1061385][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-258">Chromium issue: [#1061385][CR1090802]</span></span>  

### <span data-ttu-id="3cc1d-259">[アプリケーション] パネルでの新しいフレームの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="3cc1d-259">New frame details view in Application panel</span></span>  

<span data-ttu-id="3cc1d-260">DevTools で、各フレームの詳細ビューが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-260">DevTools now show a detailed view for each frame.</span></span>  <span data-ttu-id="3cc1d-261">これにアクセスするには、[**アプリケーション**] パネルの [**フレーム**] メニューの下でフレームを選びます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-261">To access it, choose a frame under the **Frames** menu in the **Application** panel.</span></span>  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="[アプリケーション] パネルでのフレームの新しい詳細ビュー" lightbox="../../media/2020/08/frame-details.msft.png":::
   <span data-ttu-id="3cc1d-263">[**アプリケーション**] パネルでのフレームの新しい詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="3cc1d-263">New detailed view for a frame in **Application** panel</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-264">Chromium の問題: [#1093247][CR1093247]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-264">Chromium issue: [#1093247][CR1093247]</span></span>  

#### <span data-ttu-id="3cc1d-265">開いているウィンドウのフレームの詳細</span><span class="sxs-lookup"><span data-stu-id="3cc1d-265">Frame details for opened windows</span></span>  

<span data-ttu-id="3cc1d-266">開いているウィンドウとポップアップ ウィンドウがフレーム ツリーの下にも表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-266">Open windows and pop-up windows now display under the frame tree as well.</span></span>  <span data-ttu-id="3cc1d-267">開いているウィンドウの詳細ビューには、セキュリティに関する追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-267">The detailed view of the opened windows includes additional security information.</span></span>  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="開いているウィンドウの新しいフレーム詳細ビュー" lightbox="../../media/2020/08/window-opener.msft.png":::
   <span data-ttu-id="3cc1d-269">開いているウィンドウの新しいフレーム詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="3cc1d-269">New frame detailed view for opened windows</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-270">Chromium の問題: [#1107766][CR1107766]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-270">Chromium issue: [#1107766][CR1107766]</span></span>  

#### <span data-ttu-id="3cc1d-271">セキュリティと分離に関する情報</span><span class="sxs-lookup"><span data-stu-id="3cc1d-271">Security and isolation information</span></span>  

<span data-ttu-id="3cc1d-272">セキュリティで保護されたコンテキスト、[Cross-Origin-Embedder-Policy (COEP)][WebDevCoopCoep]、[Cross-Origin-Opener-Policy (COOP)][WebDevCoopCoep] がフレーム詳細に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-272">Secure context, [Cross-Origin-Embedder-Policy (COEP)][WebDevCoopCoep], and [Cross-Origin-Opener-Policy (COOP)][WebDevCoopCoep] are now displayed in the frame details.</span></span>  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="セキュリティと分離に関する情報" lightbox="../../media/2020/08/coep-coop.msft.png":::
   <span data-ttu-id="3cc1d-274">セキュリティと分離に関する情報</span><span class="sxs-lookup"><span data-stu-id="3cc1d-274">Security and isolation information</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-275">今後、Microsoft Edge DevTools チームと Chrome DevTools チームは、フレーム詳細にさらに多くのセキュリティ情報を追加する予定です。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-275">In the future, the Microsoft Edge DevTools team and the Chrome DevTools team are planning to add more security information to the frame details.</span></span>  

<span data-ttu-id="3cc1d-276">Chromium の問題: [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-276">Chromium issue: [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="3cc1d-277">[要素] パネルと [ネットワーク] パネルの更新</span><span class="sxs-lookup"><span data-stu-id="3cc1d-277">Elements and Network panel updates</span></span>  

#### <span data-ttu-id="3cc1d-278">[スタイル] ウィンドウでのアクセシビリティに対応した色の候補</span><span class="sxs-lookup"><span data-stu-id="3cc1d-278">Accessible color suggestion in the Styles pane</span></span>  

<span data-ttu-id="3cc1d-279">DevTools では、コントラストの低い色のテキストに対して色の候補が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-279">DevTools now provides color suggestions for low color contrast text.</span></span>  

<span data-ttu-id="3cc1d-280">次の例で、`h1` のテキストにコントラストの低い色が設定されています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-280">In the example below, `h1` has low contrast text.</span></span>  <span data-ttu-id="3cc1d-281">これを修正するには、[**スタイル**] ウィンドウで `color` プロパティのカラー ピッカーを開きます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-281">To fix it, open the color picker of the `color` property in the **Styles** pane.</span></span>  <span data-ttu-id="3cc1d-282">[**コントラスト比**] セクションを展開すると、DevTools は AA と AAA の色の候補を提供します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-282">After you expand the **Contrast ratio** section, DevTools provides AA and AAA color suggestions.</span></span>  <span data-ttu-id="3cc1d-283">候補の色を選択して、色を適用します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-283">Select the suggested color to apply the color.</span></span>  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="カラー ピッカーで AA と AAA の色の候補が提示される" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   <span data-ttu-id="3cc1d-285">カラー ピッカーで AA と AAA の色の候補が提示される</span><span class="sxs-lookup"><span data-stu-id="3cc1d-285">Color picker suggests AA and AAA color suggestions</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-286">Chromium の問題: [#1093227][CR1093227]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-286">Chromium issue: [#1093227][CR1093227]</span></span>  

#### <span data-ttu-id="3cc1d-287">[要素] パネルに [プロパティ] ウィンドウを復元</span><span class="sxs-lookup"><span data-stu-id="3cc1d-287">Reinstate Properties pane in the Elements panel</span></span>  

<span data-ttu-id="3cc1d-288">[**プロパティ**] ウィンドウが復元されました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-288">The **Properties** pane is back.</span></span>  <span data-ttu-id="3cc1d-289">このウィンドウは [Microsoft Edge 84 で廃止されました][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-289">It was [deprecated in Microsoft Edge 84][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel].</span></span>  <span data-ttu-id="3cc1d-290">Microsoft Edge DevTools チームと Chrome DevTools チームは、要素のプロパティ検査のための改善を計画しています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-290">The Microsoft Edge DevTools team and the Chrome DevTools team are planning improvements for inspecting properties of elements.</span></span>  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="[要素] パネルの [プロパティ] ウィンドウ" lightbox="../../media/2020/08/properties-pane.msft.png":::
   <span data-ttu-id="3cc1d-292">[**要素**] パネルの [**プロパティ**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3cc1d-292">**Properties** pane in the **Elements** panel</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-293">Chromium の問題:</span><span class="sxs-lookup"><span data-stu-id="3cc1d-293">Chromium issue:</span></span>  <!--  [#1105205][CR1105205],  -->  <span data-ttu-id="3cc1d-294">[#1116085][CR1116085]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-294">[#1116085][CR1116085]</span></span>  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="Human-readable `X-Client-Data` header values" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### <span data-ttu-id="3cc1d-295">[スタイル] ウィンドウでのカスタム フォントのオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-295">Autocomplete custom fonts in the Styles pane</span></span>  

<span data-ttu-id="3cc1d-296">[**スタイル**] ウィンドウで `font-family` プロパティを編集するときの CSS のオートコンプリート一覧に、インポートされたフォント フェイスが追加されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-296">Imported font faces are now added to the list of CSS autocompletion when editing the `font-family` property in the **Styles** pane.</span></span>  

<span data-ttu-id="3cc1d-297">たとえば、`monospace` がローカル コンピューターにインストールされたカスタム フォントである場合、CSS コンプリート一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-297">For example, if `monospace` is a custom font installed on the local machine, it's displayed in the CSS completion list.</span></span> <span data-ttu-id="3cc1d-298">Microsoft Edge の以前のバージョンでは、フォントが表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-298">In previous versions of Microsoft Edge, the font wasn't displayed.</span></span>

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="カスタム フォントのオートコンプリート" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   <span data-ttu-id="3cc1d-300">カスタム フォントのオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="3cc1d-300">Autocomplete custom fonts</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-301">Chromium の問題: [#1106221] [CR1106221]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-301">Chromium issue: [#1106221][CR1106221]</span></span>  

#### <span data-ttu-id="3cc1d-302">[ネットワーク] パネルでリソースの種類を一貫して表示する</span><span class="sxs-lookup"><span data-stu-id="3cc1d-302">Consistently display resource type in Network panel</span></span>  

<span data-ttu-id="3cc1d-303">DevTools では、元のネットワーク要求と同じリソースの種類が一貫して表示され、リダイレクト (HTTP 状態コード 302) が発生すると [**種類**] 列の値に `/ Redirect` が追加されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-303">DevTools now consistently display the same resource type as the original network request and appends `/ Redirect` to the **Type** column value when redirection \(HTTP status code 302\) happens.</span></span>  

<span data-ttu-id="3cc1d-304">以前は、DevTools が種類を `Other` に変更する場合がありました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-304">Previously DevTools changed the type to `Other` sometimes.</span></span>  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="リダイレクト時にリソースの種類を表示する" lightbox="../../media/2020/08/network-redirect.msft.png":::
   <span data-ttu-id="3cc1d-306">リダイレクト時にリソースの種類を表示する</span><span class="sxs-lookup"><span data-stu-id="3cc1d-306">Display redirect resource type</span></span>  
:::image-end:::  

<span data-ttu-id="3cc1d-307">Chromium の問題: [#997694][CR997694]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-307">Chromium issue: [#997694][CR997694]</span></span>  

#### <span data-ttu-id="3cc1d-308">[要素] パネルと [ネットワーク] パネルのクリア ボタン</span><span class="sxs-lookup"><span data-stu-id="3cc1d-308">Clear buttons in the Elements and Network panels</span></span>  

<span data-ttu-id="3cc1d-309">次のテキスト ボックスに、[**クリア**] ボタンが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-309">The following text boxes now have **Clear** buttons.</span></span>  

*   <span data-ttu-id="3cc1d-310">[**スタイル**] ウィンドウと [**ネットワーク**] パネルのフィルター テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-310">The filter text boxes in the **Styles** pane and **Network** panel.</span></span>  
*   <span data-ttu-id="3cc1d-311">[**要素**] パネルの DOM 検索テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-311">The DOM search text box in the **Elements** panel.</span></span>  

<span data-ttu-id="3cc1d-312">[**クリア**] ボタンを選択して、入力されたテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-312">Choose the **Clear** button to remove any inputted text.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="[要素] パネルの [クリア] ボタン" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         <span data-ttu-id="3cc1d-314">[**要素**] パネルの [クリア] ボタン</span><span class="sxs-lookup"><span data-stu-id="3cc1d-314">Clear buttons in the **Elements** panels</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="[ネットワーク] パネルの [クリア] ボタン" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         <span data-ttu-id="3cc1d-316">[**ネットワーク**] パネルの [クリア] ボタン</span><span class="sxs-lookup"><span data-stu-id="3cc1d-316">Clear buttons in the  **Network** panels</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3cc1d-317">Chromium の問題: [#1067184][CR1067184]</span><span class="sxs-lookup"><span data-stu-id="3cc1d-317">Chromium issue: [#1067184][CR1067184]</span></span>  

## <span data-ttu-id="3cc1d-318">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="3cc1d-318">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="3cc1d-319">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-319">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="3cc1d-320">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-320">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="3cc1d-321">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="3cc1d-321">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools の設定アイコン"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel "[要素] パネルの [プロパティ] ウィンドウの廃止 - DevTools の新機能 (Microsoft Edge 84) | Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS グリッドのデバッグ機能 - DevTools の新機能 (Microsoft Edge 85) | Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "試験的な API を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース オーダー ビューアーを有効にする - 試験的機能 | Microsoft Docs"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式デバイスとデュアルスクリーン デバイスのテスト - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "table - コンソール API リファレンス | Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける | Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでレンダリング パフォーマンスを分析する - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsMediaPanelIndex]: /microsoft-edge/devtools-guide-chromium/media-panel/index "メディアプレーヤー情報を表示してデバッグする | Microsoft Docs"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Code の Windows 用キーボード ショートカット"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface Duo"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium bugs"
[CR384968]: https://crbug.com/384968 "local () フォントを無視するオプション | Chromium bugs"  
[CR772558]: https://crbug.com/772558 "DevTools: Lighthouse の最新バージョンに更新する | Chromium bugs"  
[CR807440]: https://crbug.com/807440 "SW の数が多いと Chrome がロックされる | Chromium bugs"  
[CR997694]: https://crbug.com/997694 "[ネットワーク] パネルの "xhr" フィルターの下に 302 状態の XHR 要求が表示されない | Chromium bugs"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/Table ツーリング | Chromium bugs"  
[CR1051466]: https://crbug.com/1051466 "DevTools での COOP/COEP デバッグのサポート | Chromium bugs"  
[CR1054281]: https://crbug.com/1054281 "機能に関する要望: DevTools で折りたたみ式デバイスとデュアルスクリーン デバイスをエミュレートできるようにしてほしい | Chromium bugs"  
[CR1067184]: https://crbug.com/1067184 "機能に関する要望: ネットワークと要素の [フィルターのクリア] ボタン > スタイル フィルター入力 | Chromium bugs"  
[CR1068116]: https://crbug.com/1068116 "☂ [問題] パネルのリリース | Chromium bugs"  
[CR1080569]: https://crbug.com/1080569 "Acorn で論理代入演算子がサポートされていない | Chromium bugs"  
[CR1080589]: https://crbug.com/1080589 "サードパーティ/ファーストパーティによる問題を分類する | Chromium bugs"  
[CR1086817]: https://crbug.com/1086817 "Acorn で数値区切り記号がサポートされていない | Chromium bugs"  
[CR1090802]: https://crbug.com/1090802 "アイドル検出 API からのアイドル状態の変更をシミュレーションする | Chromium bugs"  
[CR1093227]: https://crbug.com/1093227 "DevTools: アクセシビリティに対応した最も近い色を提案する | Chromium bugs"  
[CR1093247]: https://crbug.com/1093247 "[アプリケーション] パネルにフレームに関する情報を表示する | Chromium bugs"  
[CR1094406]: https://crbug.com/1094406 "開発者は AT のためにソース オーダー ビューアーを希望しているhttps://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools: prefers-reduced-data メディア機能のエミュレートのサポート | Chromium bugs"  
[CR1096481]: https://crbug.com/1096481 "問題バナーの配置 |Chromium bugs"  
[CR1100253]: https://crbug.com/1100253 "[要素] のコンテキスト メニューでスクリーンショット ノードのショートカットを追加する | Chromium bugs"  
[CR1103316]: https://crbug.com/1103316 "要素の検索で最初の検索結果のノード (テキストの強調表示など) が解決しない | Chromium bugs"  
[CR1103854]: https://crbug.com/1103854 "開発者ツール X クライアントデータ値の難読化を解除する | Chromium bugs"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]: https://crbug.com/1106221 「[スタイル] パネルでフォントファミリーのオートコンプリートにインポートされたフォントを追加する | Chromium bugs」  
[CR1107766]: https://crbug.com/1107766 「フレーム ツリーで 'window.open()' によって生成されたフレームに関する情報を表示する | Chromium bugs」  
[CR1115011]: https://crbug.com/1115011 「コンソールから表をコピーするときに表の構造が保持されない | Chromium bugs」  
[CR1116085]: https://crbug.com/1116085 「DevTools プロパティ検査を元に戻してください | Chromium bugs」  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "prefers-reduced-data - メディア クエリ レベル 5 | W3C CSS ワーキング グループ エディター ドラフト"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v6.2.0 - GoogleChrome/lighthouse | GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "Protocol Buffers | Google Developers"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "論理代入 | V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数値区切り記号 | V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "COOP と COEP を使用して Web サイトを \"クロスオリジン分離\" する | web.dev"  
[WebDevIdleDetection]: https://web.dev/idle-detection "アイドル検出 API で非アクティブなユーザーを検出する | web.dev"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "合成されていないアニメーションを回避する | web.dev"  

> [!NOTE]
> <span data-ttu-id="3cc1d-382">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-382">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3cc1d-383">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/08/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-383">The original page is found [here](https://developers.google.com/web/updates/2020/08/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3cc1d-385">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-385">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
