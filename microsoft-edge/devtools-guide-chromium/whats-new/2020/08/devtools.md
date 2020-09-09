---
description: キーボードショートカットを Visual Studio コードに合わせて、Surface Duo と Samsung Galaxy をエミュレートし、CSS グリッドのオーバーレイ機能を強化します。
title: DevTools の新機能 (Microsoft Edge 86)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 943eca7e73385513b264feb74ec37c450d5c5a2f
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004196"
---
# <span data-ttu-id="de972-104">DevTools の新機能 (Microsoft Edge 86)</span><span class="sxs-lookup"><span data-stu-id="de972-104">What's New In DevTools (Microsoft Edge 86)</span></span>  

## <span data-ttu-id="de972-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="de972-105">Announcements from the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### <span data-ttu-id="de972-106">DevTools のキーボードショートカットを Visual Studio コードに一致させる</span><span class="sxs-lookup"><span data-stu-id="de972-106">Match keyboard shortcuts in DevTools to Visual Studio Code</span></span>  

<span data-ttu-id="de972-107">Microsoft Edge 86 では、DevTools のキーボードショートカットが [Visual Studio コード][VisualStudioCode]のショートカットに対応している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de972-107">In Microsoft Edge 86, you may match keyboard shortcuts in the DevTools to your shortcuts in [Visual Studio Code][VisualStudioCode].</span></span> 

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   <span data-ttu-id="de972-109">DevTools for Visual Studio コードのキーボードショートカットを一致させる</span><span class="sxs-lookup"><span data-stu-id="de972-109">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="de972-110">この機能を有効にするには、 [Microsoft Edge DevTools の [キーボードショートカットのカスタマイズ][DevtoolsCustomizeShortcuts]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="de972-110">To activate this feature, navigate to [Customize keyboard shortcuts in the Microsoft Edge DevTools][DevtoolsCustomizeShortcuts].</span></span>  

<span data-ttu-id="de972-111">たとえば、 [Visual Studio コード][VisualStudioCodeShortcutsKeyboardWindows] でスクリプトを一時停止または実行し続けるためのキーボードショートカットは、 `F5` です。</span><span class="sxs-lookup"><span data-stu-id="de972-111">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualStudioCodeShortcutsKeyboardWindows] is `F5`.</span></span>  <span data-ttu-id="de972-112">**Devtools (既定)** の事前設定を使用すると、devtools でも同じショートカットが表示され `F8` ますが、 **Visual Studio のコード**プリセットを選択すると、このようにショートカットが作成され `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="de972-112">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8`, but when you choose the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="de972-113">Chromium の問題 [#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="de972-113">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="de972-114">Surface Duo と Samsung Galaxy 折りたたみのエミュレート</span><span class="sxs-lookup"><span data-stu-id="de972-114">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="de972-116">実験的機能</span><span class="sxs-lookup"><span data-stu-id="de972-116">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="de972-117">Microsoft Edge で、  [Surface Duo][MicrosoftSurfaceDevicesDuo] と [Samsung Galaxy][SamsungMobileGalaxyFold] の2つの新しいデバイスで web サイトまたはアプリの外観をテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-117">You are now able to test the look and feel of your website or app on two new devices:  [Surface Duo][MicrosoftSurfaceDevicesDuo] and [Samsung Galaxy Fold][SamsungMobileGalaxyFold] in Microsoft Edge.</span></span>  

<span data-ttu-id="de972-118">デュアル画面と折りたたみ式デバイスのために web サイトやアプリを強化するには、 [デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="de972-118">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="de972-119">[スパニング][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: web サイト \ (またはアプリ \) が両方の画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="de972-119">[Spanning][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>
*   <span data-ttu-id="de972-120">2つの画面の間の領域である[継ぎ目をレンダリング][DualScreenIntroductionHowWorkSeam]します。</span><span class="sxs-lookup"><span data-stu-id="de972-120">[Rendering the seam][DualScreenIntroductionHowWorkSeam], which is the space between the two screens.</span></span>
*   <span data-ttu-id="de972-121">[実験的な Web プラットフォーム api を有効][DevtoolsExperimentalFeaturesEnableExperimentalApis] にして、新しい [CSS メディア画面のスパニング機能][DualScreenWebCssMediaSpanning] と [JavaScript getwindowsegments api][DualScreenWebJavascriptGetwindowsegments]にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de972-121">[Enabling experimental Web Platform APIs][DevtoolsExperimentalFeaturesEnableExperimentalApis] to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments].</span></span>  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="Surface Duo のデバイスエミュレーション" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   <span data-ttu-id="de972-123">Surface Duo のデバイスエミュレーション</span><span class="sxs-lookup"><span data-stu-id="de972-123">Device emulation for Surface Duo</span></span>  
:::image-end:::  

<span data-ttu-id="de972-124">この実験的な機能を有効にするには、「 [実験的な機能を有効][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] にする」に移動し、[ **エミュレーション: Support dual screen mode**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="de972-124">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Emulation: Support dual screen mode**.</span></span>  

<span data-ttu-id="de972-125">この実験の詳細については、「 [エミュレーション: デュアルスクリーンモードのサポート][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de972-125">For more information about this experiment, navigate to [Emulation: Support dual screen mode][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode].</span></span>  

<span data-ttu-id="de972-126">Chromium の問題: [#1054281][CR1054281]</span><span class="sxs-lookup"><span data-stu-id="de972-126">Chromium issue: [#1054281][CR1054281]</span></span>  

### <span data-ttu-id="de972-127">CSS グリッドのオーバーレイの改善と新しい実験的なグリッド機能</span><span class="sxs-lookup"><span data-stu-id="de972-127">CSS grid overlay improvements and new experimental grid features</span></span>  

<span data-ttu-id="de972-128">CSS グリッドのオーバーレイの改善について、ご意見をお寄せいただきありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="de972-128">Thank you for the positive feedback about the improved CSS grid overlays.</span></span>  <span data-ttu-id="de972-129">CSS グリッドのオーバーレイは既定で有効になりました。実験を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de972-129">The CSS grid overlays are now enabled by default and do not require you to turn on an experiment.</span></span>  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="Article 要素の CSS グリッドオーバーレイ" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   <span data-ttu-id="de972-131">要素の CSS グリッドのオーバーレイ `article`</span><span class="sxs-lookup"><span data-stu-id="de972-131">CSS grid overlay for `article` element</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="de972-132">グリッドオーバーレイの詳細については、「 [CSS grid デバッグ機能][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de972-132">For more information about grid overlays, go to [CSS grid debugging features][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="de972-133">Microsoft Edge DevTools チームと Chrome DevTools チームは、その他の機能について共同作業しています。</span><span class="sxs-lookup"><span data-stu-id="de972-133">The Microsoft Edge DevTools team and the Chrome DevTools team collaborate on additional features.</span></span>  <span data-ttu-id="de972-134">新機能には、[**要素**] パネルの新しい**レイアウト**ウィンドウで永続的かつ構成可能な複数のオーバーレイが含まれています。</span><span class="sxs-lookup"><span data-stu-id="de972-134">The new features include multiple overlays that are persistent and configurable from a new **Layout** pane on the **Elements** panel.</span></span>  

<span data-ttu-id="de972-135">この実験的な機能を有効にするには、「 [実験的な機能を][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 有効にする」のチェックボックスをオンにし、[新しい CSS グリッドのデバッグ機能を有効にする] の横にあるチェックボックスをオンにします **(再起動後に、[レイアウト] サイドバーウィンドウで利用できる構成オプション)**。</span><span class="sxs-lookup"><span data-stu-id="de972-135">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable new CSS Grid debugging features (configuration options available in Layout sidebar pane in Elements after restart)**.</span></span>  

<span data-ttu-id="de972-136">この実験の詳細については、「 [新しい CSS grid デバッグ機能を有効][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de972-136">For more information about this experiment, navigate to [Enable new CSS grid debugging features][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="de972-137">Chromium の問題: [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="de972-137">Chromium issue: [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="de972-138">コンソールからコピーした表の書式が保持される</span><span class="sxs-lookup"><span data-stu-id="de972-138">Table copied from the Console preserves formatting</span></span>  

<span data-ttu-id="de972-139">Microsoft Edge 85 以前のバージョンでは、コピーの書式設定が `console.table` 失われました。</span><span class="sxs-lookup"><span data-stu-id="de972-139">In Microsoft Edge 85 or earlier, the formatting of a copied `console.table` was lost.</span></span>  <span data-ttu-id="de972-140">[表][DevtoolsConsoleApiTable]本体 API から出力をコピーして貼り付けた場合、表のテキストのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="de972-140">If you copied the output from the [table][DevtoolsConsoleApiTable] Console API, and pasted it, only the text of the table was kept.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="Microsoft Edge 85 以前の表本体 API 出力" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` <span data-ttu-id="de972-142">Microsoft Edge 85 以前の本体の API 出力</span><span class="sxs-lookup"><span data-stu-id="de972-142">Console API output in Microsoft Edge 85 or earlier</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 85 以降の表本体 API の出力が Visual Studio コードに貼り付けられています" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="de972-144">Microsoft Edge 85 またはそれ以前のバージョンの Visual Studio コードに貼り付けられた本体 API の出力</span><span class="sxs-lookup"><span data-stu-id="de972-144">Console API output from Microsoft Edge 85 or earlier pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="de972-145">Microsoft Edge 86 以降では、 **コンソール**から表をコピーすると、書式設定が保持されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-145">In Microsoft Edge 86 or later, when you copy a table from the **Console**, the formatting is now preserved.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="Microsoft Edge 86 以降の表本体 API の出力" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` <span data-ttu-id="de972-147">Microsoft Edge 86 以降の本体の API 出力</span><span class="sxs-lookup"><span data-stu-id="de972-147">Console API output in Microsoft Edge 86 or later</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 86 以降の表本体 API の出力が Visual Studio コードに貼り付けられている" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="de972-149">Microsoft Edge 86 以降で Visual Studio コードに貼り付けられた本体 API の出力</span><span class="sxs-lookup"><span data-stu-id="de972-149">Console API output from Microsoft Edge 86 or later pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="de972-150">Chromium の問題: [#1115011] [CR1115011]</span><span class="sxs-lookup"><span data-stu-id="de972-150">Chromium issue: [#1115011][CR1115011]</span></span>  

### <span data-ttu-id="de972-151">簡単なアクセシビリティテストのためのソースオーダービューアー</span><span class="sxs-lookup"><span data-stu-id="de972-151">Source Order Viewer for easier accessibility testing</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="de972-153">実験的機能</span><span class="sxs-lookup"><span data-stu-id="de972-153">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="de972-154">新しいアクセシビリティヘルパーは、ソース内の要素の順序を表示します。</span><span class="sxs-lookup"><span data-stu-id="de972-154">The new accessibility helper displays the order of elements in the source.</span></span>  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="ソース注文の表示をアクティブ化する" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   <span data-ttu-id="de972-156">**ソース注文の表示を**アクティブ化する</span><span class="sxs-lookup"><span data-stu-id="de972-156">Activate **Show source order**</span></span>  
:::image-end:::  

<span data-ttu-id="de972-157">この機能により、web サイトやアプリのスクリーンリーダーとキーボードユーザーの操作性を簡単にテストできます。</span><span class="sxs-lookup"><span data-stu-id="de972-157">This feature makes it easier to test the way screen reader and keyboard users experience your website or app.</span></span>  <span data-ttu-id="de972-158">スクリーンリーダーとキーボードナビゲーションは、web サイトまたはアプリのソースコードで特定の順序に配置されているコンテンツに依存するため、表示されているページと一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="de972-158">Screen readers and keyboard navigation depend on content being placed in a particular order in the source code of your website or app, so that it matches the rendered page.</span></span>  <span data-ttu-id="de972-159">ソースオーダービューアーには、レンダリングされたページとソースコードとの順序が異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de972-159">The Source Order Viewer displays potential differences in order between the rendered page and the source code.</span></span>  

<span data-ttu-id="de972-160">この実験的な機能を有効にするには、「 [実験的な機能を][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 有効にする」に移動し、[ **ソースオーダービューアーを有効**にする] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="de972-160">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Source Order Viewer**.</span></span>  

<span data-ttu-id="de972-161">この実験の詳細については、「 [ソースオーダービューアーを有効][DevtoolsExperimentalFeaturesEnableSourceOrderViewer]にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de972-161">For more information about this experiment, navigate to [Enable Source Order Viewer][DevtoolsExperimentalFeaturesEnableSourceOrderViewer].</span></span>  

<span data-ttu-id="de972-162">Chromium の問題: [#1094406][CR1094406]</span><span class="sxs-lookup"><span data-stu-id="de972-162">Chromium issue: [#1094406][CR1094406]</span></span>  

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

### <span data-ttu-id="de972-163">[要素] ツールですべての検索結果を強調表示する</span><span class="sxs-lookup"><span data-stu-id="de972-163">Highlight all search results in Elements tool</span></span>  

<span data-ttu-id="de972-164">Microsoft Edge 84 および85では、 **要素** パネルの最初の検索結果は強調表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="de972-164">In Microsoft Edge 84 and 85, the first search result in the **Elements** panel did not highlight.</span></span>  <span data-ttu-id="de972-165">残りの検索結果が正しく強調表示されました。</span><span class="sxs-lookup"><span data-stu-id="de972-165">The remaining search results were highlighted correctly.</span></span>  

<span data-ttu-id="de972-166">フィードバックを送信して、Chromium の改善に努めていただき、ありがとうございました。</span><span class="sxs-lookup"><span data-stu-id="de972-166">Thank you for sending your feedback and helping improve Chromium.</span></span>  <span data-ttu-id="de972-167">Chromium によって報告される [#1103316][CR1103316] 問題は、オープンソースのプロジェクトにあります。</span><span class="sxs-lookup"><span data-stu-id="de972-167">Your feedback uncovered Issue [#1103316][CR1103316] in the open-source Chromium project.</span></span>  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="Microsoft Edge 84 以降の要素パネルで強調表示された最初の検索結果" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   <span data-ttu-id="de972-169">Microsoft Edge 84 以降の **要素** パネルで強調表示された最初の検索結果</span><span class="sxs-lookup"><span data-stu-id="de972-169">Highlighted first search result on **Elements** panel in Microsoft Edge 84 or later</span></span>  
:::image-end:::  

<span data-ttu-id="de972-170">この問題は、Microsoft Edge のすべてのバージョンで修正されました。</span><span class="sxs-lookup"><span data-stu-id="de972-170">The issue is now fixed in all versions of Microsoft Edge.</span></span>  

<span data-ttu-id="de972-171">Chromium の問題: [#1103316][CR1103316]</span><span class="sxs-lookup"><span data-stu-id="de972-171">Chromium issue: [#1103316][CR1103316]</span></span>  

## <span data-ttu-id="de972-172">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="de972-172">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="de972-173">新しいメディアパネル</span><span class="sxs-lookup"><span data-stu-id="de972-173">New Media panel</span></span>  

<span data-ttu-id="de972-174">DevTools でメディアプレーヤーの情報が [メディア][DevtoolsMediaIndex] パネルに表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-174">DevTools now displays media players information in the [Media][DevtoolsMediaIndex] panel.</span></span>  

<span data-ttu-id="de972-175">新しい **メディア** パネルを開くには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de972-175">To open the new **Media** panel, complete the following step.</span></span>  

1.  <span data-ttu-id="de972-176">[**カスタマイズと制御 devtools** \ (\)] を選択して、 `...` **その他のツール**  >  **メディア**> します。</span><span class="sxs-lookup"><span data-stu-id="de972-176">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="新しいメディアパネル" lightbox="../../media/2020/08/media-panel.msft.png":::
       <span data-ttu-id="de972-178">新しい **メディア** パネル</span><span class="sxs-lookup"><span data-stu-id="de972-178">New **Media** panel</span></span>  
    :::image-end:::  

<span data-ttu-id="de972-179">DevTools の新しい **メディア** パネルの前に、ビデオプレーヤーに関するログとデバッグ情報は [ **最近のプレイヤー** ] の設定の下にありました。</span><span class="sxs-lookup"><span data-stu-id="de972-179">Before the new **Media** panel in DevTools, the logging and debug information about video players was located under the **Recent Players** setting.</span></span>  <span data-ttu-id="de972-180">「 **最近** 」のプレイヤーの設定を開くには、「 `edge://media-internals` players ( **プレーヤー** )」タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="de972-180">To open the **Recent Players** setting, go to `edge://media-internals` and choose the **Players** tab.</span></span>  

<span data-ttu-id="de972-181">ライブコンテンツを表示して、次の例を含む、潜在的な問題をより迅速に検査します。</span><span class="sxs-lookup"><span data-stu-id="de972-181">View live content and inspect potential issues more quickly, including the following examples.</span></span>  

*   <span data-ttu-id="de972-182">フレームが削除されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="de972-182">Why frames are dropped?</span></span>  
*   <span data-ttu-id="de972-183">JavaScript が予期しない方法でプレーヤーとやり取りしているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="de972-183">Why JavaScript is interacting with the player in an unexpected way?</span></span>  

### <span data-ttu-id="de972-184">[要素] パネルのコンテキストメニューを使用したノードのスクリーンショットのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="de972-184">Capture node screenshots using the Elements panel context menu</span></span>  

<span data-ttu-id="de972-185">[ **要素** ] パネルのコンテキストメニューを使って、ノードのスクリーンショットをキャプチャできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-185">You may now capture node screenshots using the context menu in the **Elements** panel.</span></span>  

<span data-ttu-id="de972-186">たとえば、目次のスクリーンショットを撮るには、要素をポイントしてコンテキストメニューを開き (\ を右クリックし)、[ **キャプチャノードのスクリーンショット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de972-186">For example, to take a screenshot of the table of contents, hover on the element, open the contextual menu \(right-click\), and select **Capture node screenshot**.</span></span>  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="キャプチャノードのスクリーンショット" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   <span data-ttu-id="de972-188">キャプチャノードのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="de972-188">Capture node screenshots</span></span>  
:::image-end:::  

<span data-ttu-id="de972-189">Chromium の問題: [#1100253][CR1100253]</span><span class="sxs-lookup"><span data-stu-id="de972-189">Chromium issue: [#1100253][CR1100253]</span></span>  

### <span data-ttu-id="de972-190">問題ツールの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="de972-190">Issues tool updates</span></span>  

<span data-ttu-id="de972-191">**コンソール**パネルの問題の警告バーは、通常のメッセージに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="de972-191">The Issues warning bar on the **Console** panel is now replaced with a regular message.</span></span>  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text="コンソールメッセージの問題" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   <span data-ttu-id="de972-193">コンソールメッセージの問題</span><span class="sxs-lookup"><span data-stu-id="de972-193">Issues in console message</span></span>  
:::image-end:::  

<span data-ttu-id="de972-194">サードパーティの cookie の問題は、[ **問題** ] ツールで既定で非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="de972-194">Third-party cookie issues are now hidden by default in the **Issues** tool.</span></span>  <span data-ttu-id="de972-195">[ **サードパーティの cookie の追加の問題** ] チェックボックスをオンにして、問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="de972-195">Enable the new **Include third-party cookie issues** checkbox to view the issues.</span></span>  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="サードパーティの cookie の問題チェックボックス" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   <span data-ttu-id="de972-197">サードパーティの cookie の問題チェックボックス</span><span class="sxs-lookup"><span data-stu-id="de972-197">third-party cookie issues checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="de972-198">Chromium の問題: [1096481][CR1096481]、 [1068116][CR1068116]、 [1080589][CR1080589]</span><span class="sxs-lookup"><span data-stu-id="de972-198">Chromium issues: [1096481][CR1096481], [1068116][CR1068116], [1080589][CR1080589]</span></span>  

### <span data-ttu-id="de972-199">見つからないローカルフォントのエミュレート</span><span class="sxs-lookup"><span data-stu-id="de972-199">Emulate missing local fonts</span></span>  

<span data-ttu-id="de972-200">[レンダリングツール][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]を開いて、[新しい**ローカルフォントの無効化**] 機能を使用して、 `local()` ルールに含まれないソースをエミュレートし `@font-face` ます。</span><span class="sxs-lookup"><span data-stu-id="de972-200">Open the [Rendering tool][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] and use the new **Disable local fonts** feature to emulate missing `local()` sources in `@font-face` rules.</span></span>  

<span data-ttu-id="de972-201">たとえば、デバイスにフォントがインストールされていて、ルールによってフォントとして使用されている場合、 `Rubik` `@font-face src` `local()` Microsoft Edge では、デバイスのローカルフォントファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="de972-201">For example, when the `Rubik` font is installed on your device and the `@font-face src` rule uses it as a `local()` font, Microsoft Edge uses the local font file from your device.</span></span>  

<span data-ttu-id="de972-202">[ **ローカルフォントを無効** にする] が有効になっている場合、devtools ではフォントが無視され、 `local()` 各ネットワークからの取り出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="de972-202">When **Disable local fonts** is enabled, DevTools ignores the `local()` fonts and fetches each from the network.</span></span>  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="見つからないローカルフォントのエミュレート" lightbox="../../media/2020/08/disable-font.msft.png":::
   <span data-ttu-id="de972-204">見つからないローカルフォントのエミュレート</span><span class="sxs-lookup"><span data-stu-id="de972-204">Emulate missing local fonts</span></span>  
:::image-end:::  

<span data-ttu-id="de972-205">開発中に同じフォントの2つのコピーを使う場合は、次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="de972-205">If you use two different copies of the same font during development, such as the following examples.</span></span>  

*   <span data-ttu-id="de972-206">デザインツールのローカルフォント。</span><span class="sxs-lookup"><span data-stu-id="de972-206">A local font for your design tools.</span></span>  
*   <span data-ttu-id="de972-207">コードの web フォント。</span><span class="sxs-lookup"><span data-stu-id="de972-207">A web font for your code.</span></span>  

<span data-ttu-id="de972-208">[ **ローカルフォントの無効化** ] を使用して、次の作業を簡単に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="de972-208">Use **Disable local fonts** to make it easier for you to complete the following tasks.</span></span>  

*   <span data-ttu-id="de972-209">ロードパフォーマンスと web フォントの最適化をデバッグして計測します。</span><span class="sxs-lookup"><span data-stu-id="de972-209">Debug and measure loading performance and optimization of web fonts.</span></span>  
*   <span data-ttu-id="de972-210">CSS ルールの精度を確認 `@font-face` します。</span><span class="sxs-lookup"><span data-stu-id="de972-210">Verify accuracy of your CSS `@font-face` rules.</span></span>  
*   <span data-ttu-id="de972-211">デバイスにインストールされているローカルバージョンと web フォントの違いを見つけます。</span><span class="sxs-lookup"><span data-stu-id="de972-211">Discover differences between local versions installed on your device and a web font.</span></span>  

<span data-ttu-id="de972-212">Chromium の問題: [#384968][CR384968]</span><span class="sxs-lookup"><span data-stu-id="de972-212">Chromium issue: [#384968][CR384968]</span></span>  

### <span data-ttu-id="de972-213">アクティブでないユーザーのエミュレート</span><span class="sxs-lookup"><span data-stu-id="de972-213">Emulate inactive users</span></span>  

<span data-ttu-id="de972-214">[アイドル検出 API][WebDevIdleDetection]を使うと、開発者は非アクティブなユーザーを検出し、アイドル状態の変更を反映することができます。</span><span class="sxs-lookup"><span data-stu-id="de972-214">The [Idle Detection API][WebDevIdleDetection] allows developers to detect inactive users and react on idle state changes.</span></span>  <span data-ttu-id="de972-215">この時点で、DevTools を使って、 **センサー** ツールでのアイドル状態の変更を、ユーザーの状態と画面の状態の両方に対してエミュレートすることができるようになりました。これは、実際のアイドル状態が変更されるのを待機する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de972-215">You are now able to use DevTools to emulate idle state changes in the **Sensors** tool for both the user state and the screen state instead of waiting for the actual idle state to change.</span></span>  <span data-ttu-id="de972-216">[引き出し][DevtoolsCustomizeIndexDrawer]から**センサー**ツールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="de972-216">You may open the **Sensors** tool from the [Drawer][DevtoolsCustomizeIndexDrawer].</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="アクティブでないユーザーのエミュレート" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   <span data-ttu-id="de972-218">アクティブでないユーザーのエミュレート</span><span class="sxs-lookup"><span data-stu-id="de972-218">Emulate inactive users</span></span>  
:::image-end:::  

<span data-ttu-id="de972-219">Chromium の問題: [#1090802][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="de972-219">Chromium issue: [#1090802][CR1090802]</span></span>  

### <span data-ttu-id="de972-220">割引の優先のエミュレート-データ</span><span class="sxs-lookup"><span data-stu-id="de972-220">Emulate prefers-reduced-data</span></span>  

> [!NOTE]
> <span data-ttu-id="de972-221">Microsoft Edge 86 でこの機能を有効にするには、「 `edge://flags#enable-experimental-web-platform-features` 実験的な **Web Platform 機能** 」フラグをオンにして有効にします。</span><span class="sxs-lookup"><span data-stu-id="de972-221">In Microsoft Edge 86, to enable this feature, go to `edge://flags#enable-experimental-web-platform-features` and turn on the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="de972-222">エミュレーションオプションは、フラグが有効になっている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="de972-222">The emulation option is only displayed if the flag is enabled.</span></span>  

<span data-ttu-id="de972-223">データ削減の [優先][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] メディアクエリは、データを減らしたユーザーのコンテンツ設定を検出します。</span><span class="sxs-lookup"><span data-stu-id="de972-223">The [prefers-reduced-data][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] media query detects user content preferences for reduced data.</span></span>  <span data-ttu-id="de972-224">選択されている場合、ユーザーは、少ないデータを使用する代替ページコンテンツを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="de972-224">If selected, the user receives alternate page content that uses less data.</span></span>  

<span data-ttu-id="de972-225">これで、DevTools を使ってメディアクエリをエミュレートでき `prefers-reduced-data` ます。</span><span class="sxs-lookup"><span data-stu-id="de972-225">You may now use DevTools to emulate the `prefers-reduced-data` media query.</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="割引の優先のエミュレート-データ" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   <span data-ttu-id="de972-227">割引の優先のエミュレート-データ</span><span class="sxs-lookup"><span data-stu-id="de972-227">Emulate prefers-reduced-data</span></span>  
:::image-end:::  

<span data-ttu-id="de972-228">Chromium の問題: [#1096068][CR1096068]</span><span class="sxs-lookup"><span data-stu-id="de972-228">Chromium issue: [#1096068][CR1096068]</span></span>  

### <span data-ttu-id="de972-229">新しい JavaScript 機能のサポート</span><span class="sxs-lookup"><span data-stu-id="de972-229">Support for new JavaScript features</span></span>  

<span data-ttu-id="de972-230">DevTools では、次の JavaScript 言語機能がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-230">DevTools now have better supported the following JavaScript language features.</span></span>  

| <span data-ttu-id="de972-231">JavaScript 言語機能</span><span class="sxs-lookup"><span data-stu-id="de972-231">JavaScript language feature</span></span> | <span data-ttu-id="de972-232">詳細</span><span class="sxs-lookup"><span data-stu-id="de972-232">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="de972-233">論理代入演算子</span><span class="sxs-lookup"><span data-stu-id="de972-233">Logical assignment operators</span></span>][V8FeaturesLogicalAssignment] | <span data-ttu-id="de972-234">DevTools は、 `&&=` `||=` `??=` **本体** と **ソース** パネルでの新しい演算子、and 演算子による論理割り当てをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-234">DevTools now supports logical assignment with the new `&&=`, `||=`, and `??=` operators in the **Console** and **Sources** panels.</span></span>  |  
| <span data-ttu-id="de972-235">[数値の区切り記号][V8FeaturesNumericSeparators]を整形して印刷する</span><span class="sxs-lookup"><span data-stu-id="de972-235">Pretty-print [numeric separators][V8FeaturesNumericSeparators]</span></span> | <span data-ttu-id="de972-236">DevTools では、[ **ソース** ] パネルで数値の区切り記号が適切に印刷されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-236">DevTools now properly pretty-prints the numeric separators in the **Sources** panel.</span></span>  |  

<span data-ttu-id="de972-237">Chromium の問題: [1086817][CR1086817]、 [1080569][CR1080569]</span><span class="sxs-lookup"><span data-stu-id="de972-237">Chromium issues: [1086817][CR1086817], [1080569][CR1080569]</span></span>  

### <span data-ttu-id="de972-238">Lighthouse パネルの Lighthouse 6.2</span><span class="sxs-lookup"><span data-stu-id="de972-238">Lighthouse 6.2 in the Lighthouse panel</span></span>  

<span data-ttu-id="de972-239">**Lighthouse** panel で、Lighthouse 6.2 が実行されています。</span><span class="sxs-lookup"><span data-stu-id="de972-239">The **Lighthouse** panel is now running Lighthouse 6.2.</span></span>  <span data-ttu-id="de972-240">すべての変更の一覧については、 [Lighthouse のリリースノート][GithubGooglechromeLighthouseV620]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de972-240">For a full list of changes, go to the [Lighthouse release notes][GithubGooglechromeLighthouseV620].</span></span>  

<span data-ttu-id="de972-241">Chromium の問題: [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="de972-241">Chromium issue: [#772558][CR772558]</span></span>  

### <span data-ttu-id="de972-242">[サービス Worker] ウィンドウの他の元のリストの廃止</span><span class="sxs-lookup"><span data-stu-id="de972-242">Deprecation of other origins listing in the Service Workers pane</span></span>  

<span data-ttu-id="de972-243">DevTools では、[ **サービス作業者** ] ウィンドウからのリンクを提供します。 (**アプリケーション** パネル > [ **サービス作業** ] ウィンドウ \)、他の元からのサービスワーカーの完全な一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de972-243">DevTools now provides a link from the **Service workers** pane \(**Application** panel > **Service workers** pane\) to view the full list of service workers from other origins.</span></span>  <span data-ttu-id="de972-244">DevTools を開かずにリストにアクセスするには、に移動 `edge://service-worker-internals/?devtools` します。</span><span class="sxs-lookup"><span data-stu-id="de972-244">To access the list without opening the DevTools, go to `edge://service-worker-internals/?devtools`.</span></span>  

<span data-ttu-id="de972-245">以前の DevTools は、 **アプリケーション** パネル > **Service worker** ] ウィンドウの下に入れ子になっているリストを表示していました。</span><span class="sxs-lookup"><span data-stu-id="de972-245">Previously DevTools displayed a list nested under the **Application** panel > **Service workers** pane.</span></span>  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="他のオリジンとのリンク" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   <span data-ttu-id="de972-247">他のオリジンとのリンク</span><span class="sxs-lookup"><span data-stu-id="de972-247">Link to other origins</span></span>  
:::image-end:::  

<span data-ttu-id="de972-248">Chromium の問題: [#807440][CR807440]</span><span class="sxs-lookup"><span data-stu-id="de972-248">Chromium issue: [#807440][CR807440]</span></span>  

### <span data-ttu-id="de972-249">フィルター処理されたアイテムのカバレッジの概要を表示する</span><span class="sxs-lookup"><span data-stu-id="de972-249">Show coverage summary for filtered items</span></span>  

<span data-ttu-id="de972-250">DevTools は、更新されたカバレッジ情報の概要を動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="de972-250">DevTools now recalculate and display a summary of coverage information dynamically.</span></span>  <span data-ttu-id="de972-251">動的表示は、 [カバレッジ][DevtoolsCoverageIndex] ツールでフィルターが適用されたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="de972-251">The dynamic display is triggered when filters are applied in the [Coverage][DevtoolsCoverageIndex] tool.</span></span>  <span data-ttu-id="de972-252">**補充**ツールには、常にすべての補充情報の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de972-252">Before the **Coverage** tool always displayed a summary of all coverage information.</span></span>  

<span data-ttu-id="de972-253">次の図の最初の図では、最初に概要が表示され、 `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` 次の図の2番目に概要が表示され `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` ます。</span><span class="sxs-lookup"><span data-stu-id="de972-253">In the first of the following figures, the summary initially displays `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` and in the second of the following figures, the summary displays `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` after CSS filtering is applied.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="カバレッジの概要" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         <span data-ttu-id="de972-255">カバレッジの概要</span><span class="sxs-lookup"><span data-stu-id="de972-255">Coverage summary</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="フィルター処理されたアイテムのカバレッジの概要" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         <span data-ttu-id="de972-257">フィルター処理されたアイテムのカバレッジの概要</span><span class="sxs-lookup"><span data-stu-id="de972-257">Coverage summary for filtered items</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="de972-258">Chromium の問題: [#1061385][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="de972-258">Chromium issue: [#1061385][CR1090802]</span></span>  

### <span data-ttu-id="de972-259">アプリケーションパネルの新しいフレームの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="de972-259">New frame details view in Application panel</span></span>  

<span data-ttu-id="de972-260">DevTools には、各フレームの詳細ビューが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-260">DevTools now show a detailed view for each frame.</span></span>  <span data-ttu-id="de972-261">このアプリにアクセスするには、**アプリケーション**パネルの**フレーム**メニューの下にあるフレームを選択します。</span><span class="sxs-lookup"><span data-stu-id="de972-261">To access it, choose a frame under the **Frames** menu in the **Application** panel.</span></span>  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="アプリケーションパネルのフレームの新しい詳細表示" lightbox="../../media/2020/08/frame-details.msft.png":::
   <span data-ttu-id="de972-263">**アプリケーション**パネルのフレームの新しい詳細表示</span><span class="sxs-lookup"><span data-stu-id="de972-263">New detailed view for a frame in **Application** panel</span></span>  
:::image-end:::  

<span data-ttu-id="de972-264">Chromium の問題: [#1093247][CR1093247]</span><span class="sxs-lookup"><span data-stu-id="de972-264">Chromium issue: [#1093247][CR1093247]</span></span>  

#### <span data-ttu-id="de972-265">開いているウィンドウのフレームの詳細</span><span class="sxs-lookup"><span data-stu-id="de972-265">Frame details for opened windows</span></span>  

<span data-ttu-id="de972-266">ウィンドウを開くと、フレームツリーにも表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-266">Open windows and pop-up windows now display under the frame tree as well.</span></span>  <span data-ttu-id="de972-267">開いているウィンドウの詳細ビューには、追加のセキュリティ情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de972-267">The detailed view of the opened windows includes additional security information.</span></span>  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="開いているウィンドウの新しいフレームの詳細ビュー" lightbox="../../media/2020/08/window-opener.msft.png":::
   <span data-ttu-id="de972-269">開いているウィンドウの新しいフレームの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="de972-269">New frame detailed view for opened windows</span></span>  
:::image-end:::  

<span data-ttu-id="de972-270">Chromium の問題: [#1107766] [CR1107766]</span><span class="sxs-lookup"><span data-stu-id="de972-270">Chromium issue: [#1107766][CR1107766]</span></span>  

#### <span data-ttu-id="de972-271">セキュリティと分離に関する情報</span><span class="sxs-lookup"><span data-stu-id="de972-271">Security and isolation information</span></span>  

<span data-ttu-id="de972-272">セキュリティで保護されたコンテキスト、 [クロスオリジン-ポリシー (COEP)][WebDevCoopCoep]、および [クロスオリジン-Opener-ポリシー (co-op)][WebDevCoopCoep] がフレームの詳細に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-272">Secure context, [Cross-Origin-Embedder-Policy (COEP)][WebDevCoopCoep], and [Cross-Origin-Opener-Policy (COOP)][WebDevCoopCoep] are now displayed in the frame details.</span></span>  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="セキュリティと分離に関する情報" lightbox="../../media/2020/08/coep-coop.msft.png":::
   <span data-ttu-id="de972-274">セキュリティと分離に関する情報</span><span class="sxs-lookup"><span data-stu-id="de972-274">Security and isolation information</span></span>  
:::image-end:::  

<span data-ttu-id="de972-275">今後、Microsoft Edge DevTools チームと Chrome DevTools チームは、フレームの詳細により多くのセキュリティ情報を追加する予定です。</span><span class="sxs-lookup"><span data-stu-id="de972-275">In the future, the Microsoft Edge DevTools team and the Chrome DevTools team are planning to add more security information to the frame details.</span></span>  

<span data-ttu-id="de972-276">Chromium の問題: [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="de972-276">Chromium issue: [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="de972-277">要素とネットワークパネルの更新</span><span class="sxs-lookup"><span data-stu-id="de972-277">Elements and Network panel updates</span></span>  

#### <span data-ttu-id="de972-278">[スタイル] ウィンドウのアクセシビリティに対応した色の候補</span><span class="sxs-lookup"><span data-stu-id="de972-278">Accessible color suggestion in the Styles pane</span></span>  

<span data-ttu-id="de972-279">DevTools では、色の低いコントラストのテキストの色の候補が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-279">DevTools now provides color suggestions for low color contrast text.</span></span>  

<span data-ttu-id="de972-280">次の例で `h1` は、コントラストの低いテキストが設定されています。</span><span class="sxs-lookup"><span data-stu-id="de972-280">In the example below, `h1` has low contrast text.</span></span>  <span data-ttu-id="de972-281">修正するには、 `color` [ **スタイル** ] ウィンドウでプロパティのカラーピッカーを開きます。</span><span class="sxs-lookup"><span data-stu-id="de972-281">To fix it, open the color picker of the `color` property in the **Styles** pane.</span></span>  <span data-ttu-id="de972-282">[ **コントラスト比** ] セクションを展開すると、DEVTOOLS で AA と AAA の色候補が提供されます。</span><span class="sxs-lookup"><span data-stu-id="de972-282">After you expand the **Contrast ratio** section, DevTools provides AA and AAA color suggestions.</span></span>  <span data-ttu-id="de972-283">色を適用する色を選択します。</span><span class="sxs-lookup"><span data-stu-id="de972-283">Select the suggested color to apply the color.</span></span>  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="色のピッカーで AA と AAA の色候補が提示される" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   <span data-ttu-id="de972-285">色のピッカーで AA と AAA の色候補が提示される</span><span class="sxs-lookup"><span data-stu-id="de972-285">Color picker suggests AA and AAA color suggestions</span></span>  
:::image-end:::  

<span data-ttu-id="de972-286">Chromium の問題: [#1093227][CR1093227]</span><span class="sxs-lookup"><span data-stu-id="de972-286">Chromium issue: [#1093227][CR1093227]</span></span>  

#### <span data-ttu-id="de972-287">[要素] パネルの [復元のプロパティ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="de972-287">Reinstate Properties pane in the Elements panel</span></span>  

<span data-ttu-id="de972-288">[ **プロパティ** ] ウィンドウが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="de972-288">The **Properties** pane is back.</span></span>  <span data-ttu-id="de972-289">[Microsoft Edge 84 では廃止][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]されました。</span><span class="sxs-lookup"><span data-stu-id="de972-289">It was [deprecated in Microsoft Edge 84][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel].</span></span>  <span data-ttu-id="de972-290">Microsoft Edge DevTools チームと Chrome DevTools チームは、要素の検査プロパティの改善を計画しています。</span><span class="sxs-lookup"><span data-stu-id="de972-290">The Microsoft Edge DevTools team and the Chrome DevTools team are planning improvements for inspecting properties of elements.</span></span>  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="[要素] パネルの [プロパティ] ウィンドウ" lightbox="../../media/2020/08/properties-pane.msft.png":::
   <span data-ttu-id="de972-292">[**要素**] パネルの [**プロパティ**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="de972-292">**Properties** pane in the **Elements** panel</span></span>  
:::image-end:::  

<span data-ttu-id="de972-293">Chromium の問題:</span><span class="sxs-lookup"><span data-stu-id="de972-293">Chromium issue:</span></span>  <!--  [#1105205][CR1105205],  -->  <span data-ttu-id="de972-294">[#1116085][CR1116085]</span><span class="sxs-lookup"><span data-stu-id="de972-294">[#1116085][CR1116085]</span></span>  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="Human-readable `X-Client-Data` header values" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### <span data-ttu-id="de972-295">[スタイル] ウィンドウでのユーザー設定のフォントのオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="de972-295">Autocomplete custom fonts in the Styles pane</span></span>  

<span data-ttu-id="de972-296">`font-family`[**スタイル**] ウィンドウでプロパティを編集すると、インポートされたフォントフェイスが CSS のオートコンプリートの一覧に追加されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-296">Imported font faces are now added to the list of CSS autocompletion when editing the `font-family` property in the **Styles** pane.</span></span>  

<span data-ttu-id="de972-297">たとえば、 `monospace` カスタムフォントがローカルコンピューターにインストールされている場合は、CSS コンプリートリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="de972-297">For example, if `monospace` is a custom font installed on the local machine, it's displayed in the CSS completion list.</span></span> <span data-ttu-id="de972-298">以前のバージョンの Microsoft Edge では、フォントは表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="de972-298">In previous versions of Microsoft Edge, the font wasn't displayed.</span></span>

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="オートコンプリートのカスタムフォント" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   <span data-ttu-id="de972-300">オートコンプリートのカスタムフォント</span><span class="sxs-lookup"><span data-stu-id="de972-300">Autocomplete custom fonts</span></span>  
:::image-end:::  

<span data-ttu-id="de972-301">Chromium の問題: [#1106221] [CR1106221]</span><span class="sxs-lookup"><span data-stu-id="de972-301">Chromium issue: [#1106221][CR1106221]</span></span>  

#### <span data-ttu-id="de972-302">[ネットワーク] パネルでのリソースの種類の一貫した表示</span><span class="sxs-lookup"><span data-stu-id="de972-302">Consistently display resource type in Network panel</span></span>  

<span data-ttu-id="de972-303">DevTools では、元のネットワーク要求と同じリソースの種類が一貫して表示されるようになりまし `/ Redirect` た。リダイレクション \ (HTTP 状態コード 302) が発生したときに **type** 列の値が追加されます。</span><span class="sxs-lookup"><span data-stu-id="de972-303">DevTools now consistently display the same resource type as the original network request and appends `/ Redirect` to the **Type** column value when redirection \(HTTP status code 302\) happens.</span></span>  

<span data-ttu-id="de972-304">以前の DevTools によって型が変わる場合がありました `Other` 。</span><span class="sxs-lookup"><span data-stu-id="de972-304">Previously DevTools changed the type to `Other` sometimes.</span></span>  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="リダイレクトリソースの種類を表示する" lightbox="../../media/2020/08/network-redirect.msft.png":::
   <span data-ttu-id="de972-306">リダイレクトリソースの種類を表示する</span><span class="sxs-lookup"><span data-stu-id="de972-306">Display redirect resource type</span></span>  
:::image-end:::  

<span data-ttu-id="de972-307">Chromium の問題: [#997694][CR997694]</span><span class="sxs-lookup"><span data-stu-id="de972-307">Chromium issue: [#997694][CR997694]</span></span>  

#### <span data-ttu-id="de972-308">要素とネットワークパネルのボタンをクリアする</span><span class="sxs-lookup"><span data-stu-id="de972-308">Clear buttons in the Elements and Network panels</span></span>  

<span data-ttu-id="de972-309">次のテキストボックスには、 **クリア** ボタンが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de972-309">The following text boxes now have **Clear** buttons.</span></span>  

*   <span data-ttu-id="de972-310">[ **スタイル** ] ウィンドウと [ **ネットワーク** ] パネルのフィルターテキストボックス。</span><span class="sxs-lookup"><span data-stu-id="de972-310">The filter text boxes in the **Styles** pane and **Network** panel.</span></span>  
*   <span data-ttu-id="de972-311">[ **要素** ] パネルの DOM 検索テキストボックス。</span><span class="sxs-lookup"><span data-stu-id="de972-311">The DOM search text box in the **Elements** panel.</span></span>  

<span data-ttu-id="de972-312">[ **クリア** ] ボタンを選択して、入力されテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="de972-312">Choose the **Clear** button to remove any inputted text.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="[要素] パネルの [クリア] ボタン" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         <span data-ttu-id="de972-314">[ **要素** ] パネルの [クリア] ボタン</span><span class="sxs-lookup"><span data-stu-id="de972-314">Clear buttons in the **Elements** panels</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="ネットワークパネルのボタンをクリアする" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         <span data-ttu-id="de972-316">**ネットワーク**パネルのボタンをクリアする</span><span class="sxs-lookup"><span data-stu-id="de972-316">Clear buttons in the  **Network** panels</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="de972-317">Chromium の問題: [#1067184][CR1067184]</span><span class="sxs-lookup"><span data-stu-id="de972-317">Chromium issue: [#1067184][CR1067184]</span></span>  

## <span data-ttu-id="de972-318">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="de972-318">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="de972-319">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="de972-319">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="de972-320">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="de972-320">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="de972-321">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="de972-321">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools の設定アイコン"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel "[要素] パネルの [プロパティ] ウィンドウの廃止-DevTools の新機能 (Microsoft Edge 84) |Microsoft ドキュメント"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS grid のデバッグ機能-DevTools の新機能 (Microsoft Edge 85) |Microsoft ドキュメント"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "実験的な Api を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース注文ビューアーを有効にする-実験的な機能 |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式とデュアルスクリーンデバイスでのテスト-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験的な機能を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-コンソール API リファレンス |Microsoft ドキュメント"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブを使用して、使用されていない JavaScript と CSS コードを見つけます。Microsoft ドキュメント"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドローワ-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブの [パフォーマンス分析] 参照で、レンダリングのパフォーマンスを分析します。Microsoft ドキュメント"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "メディアプレーヤー情報を表示してデバッグする |Microsoft ドキュメント"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "Seam の操作方法-デュアルスクリーンデバイスの概要 |Microsoft ドキュメント"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "CSS メディア画面のスパン機能で、デュアルスクリーン検出Microsoft ドキュメント"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーンデバイス用の getWindowSegments JavaScript API |Microsoft ドキュメント"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio コード "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Windows 用 Visual Studio コードのキーボードショートカット"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface Duo"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボードショートカット/キーバインディングのカスタマイズを許可する |Chromium のバグ"
[CR384968]: https://crbug.com/384968 "ローカル () フォントを無視するオプションChromium のバグ"  
[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する |Chromium のバグ"  
[CR807440]: https://crbug.com/807440 "Chrome では、多数の SWs | を使ってロックするChromium のバグ"  
[CR997694]: https://crbug.com/997694 "[ネットワーク] パネルの \ "xhr \" フィルターの下に、302状態の XHR 要求が表示されません。Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table ツール"  
[CR1051466]: https://crbug.com/1051466 "DevTools での CO-OP/COEP のデバッグのサポート |Chromium のバグ"  
[CR1054281]: https://crbug.com/1054281 "機能の要求: DevTools では、折りたたみ式とデュアルスクリーンデバイスをエミュレートする必要があります。Chromium のバグ"  
[CR1067184]: https://crbug.com/1067184 "機能の要求: ネットワーク & 要素で [フィルターのクリア] ボタンを > スタイルフィルターの入力 |Chromium のバグ"  
[CR1068116]: https://crbug.com/1068116 "☂出荷問題] パネル |Chromium のバグ"  
[CR1080569]: https://crbug.com/1080569 "acorn は論理代入演算子をサポートしていません |Chromium のバグ"  
[CR1080589]: https://crbug.com/1080589 "サードパーティ/ファーストパーティで問題を分類する |Chromium のバグ"  
[CR1086817]: https://crbug.com/1086817 "acorn では、数字の区切り文字はサポートされません |Chromium のバグ"  
[CR1090802]: https://crbug.com/1090802 "Idle Detection API からのアイドル状態の変更をシミュレートする |Chromium のバグ"  
[CR1093227]: https://crbug.com/1093227 "DevTools: アクセシビリティの高い色を提案する |Chromium のバグ"  
[CR1093247]: https://crbug.com/1093247 "アプリケーションパネルのフレームに関する情報を表示する |Chromium のバグ"  
[CR1094406]: https://crbug.com/1094406 "開発者は、でのソース注文ビューアーの使用を希望 https://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools: 低優先データメディア機能のエミュレートのサポート |Chromium のバグ"  
[CR1096481]: https://crbug.com/1096481 "バナーの配置の問題 |Chromium のバグ"  
[CR1100253]: https://crbug.com/1100253 "要素のコンテキストメニューで [スクリーンショット] ノードショートカットを追加する |Chromium のバグ"  
[CR1103316]: https://crbug.com/1103316 "要素の検索では、最初の検索結果で resolveNode (テキストを強調表示するなど) はできません。Chromium のバグ"  
[CR1103854]: https://crbug.com/1103854 ""開発者ツール" の非難読化される X-クライアントデータ値Chromium のバグ"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]: https://crbug.com/1106221 "[スタイル] パネルで、[フォントファミリのオートコンプリートにインポートされたフォントを追加します] |Chromium のバグ  
[CR1107766]: https://crbug.com/1107766 "ウィンドウによって生成されたフレームについての情報を表示します。Chromium のバグ  
[CR1115011]: https://crbug.com/1115011 "コンソールからテーブルをコピーするときに、テーブルの構造は保持されません。Chromium のバグ  
[CR1116085]: https://crbug.com/1116085 "DevTools プロパティ検査をもう一度お手元にお寄せください |Chromium のバグ  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "低優先データメディアクエリレベル 5 |W3C CSS ワーキンググループエディターの下書き"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v 6.2.0-GoogleChrome/lighthouse |GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "プロトコルバッファー |Google 開発者"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy 折りたたみ |Samsung US"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "論理的な割り当て |V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数値の区切り文字 |V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "Web サイトの作成 \ "クロスオリジン分離" (CO-OP と COEP を使用) |web.xml"  
[WebDevIdleDetection]: https://web.dev/idle-detection "アイドル検出 API を使用して非アクティブなユーザーを検出する |web.xml"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "合成しないアニメーションを避けます。web.xml"  

> [!NOTE]
> <span data-ttu-id="de972-382">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="de972-382">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="de972-383">元のページは [ここ](https://developers.google.com/web/updates/2020/08/devtools/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。</span><span class="sxs-lookup"><span data-stu-id="de972-383">The original page is found [here](https://developers.google.com/web/updates/2020/08/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="de972-385">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="de972-385">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
