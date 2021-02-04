---
description: 新しい CSS グリッド デバッグ ツール、Webauthn ツール、移動可能なツール、コンピューティングサイドバー パネル。
title: DevTools の新機能 (Microsoft Edge 87)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cf3a685a1a4e9a3f13d2401a6294058a71dd5104
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313031"
---
# <span data-ttu-id="f479f-104">DevTools の新機能 (Microsoft Edge 87)</span><span class="sxs-lookup"><span data-stu-id="f479f-104">What's New In DevTools (Microsoft Edge 87)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <span data-ttu-id="f479f-105">DevTools ローカライズの改善</span><span class="sxs-lookup"><span data-stu-id="f479f-105">Improving DevTools localization</span></span>  

<span data-ttu-id="f479f-106">Microsoft Edge DevTools チームは、翻訳のニーズを満たすために、翻訳品質の向上に重点を置いしています。</span><span class="sxs-lookup"><span data-stu-id="f479f-106">To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.</span></span>  <span data-ttu-id="f479f-107">Microsoft Edge バージョン 87 から、いくつかの文字列と用語がロックされ、残りの DevTools が他の言語で表示されている場合でも変更されません。</span><span class="sxs-lookup"><span data-stu-id="f479f-107">Starting in Microsoft Edge version 87, several strings and terms are locked and do not change even when the rest of the DevTools are displayed in other languages.</span></span>  <span data-ttu-id="f479f-108">影響を受ける文字列と用語の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f479f-108">The list of affected strings and terms include the following.</span></span>  

*   <span data-ttu-id="f479f-109">[大島] **ツールの** 文字列。</span><span class="sxs-lookup"><span data-stu-id="f479f-109">The strings in the **Lighthouse** tool.</span></span>  
*   <span data-ttu-id="f479f-110">用語 `service worker` 。</span><span class="sxs-lookup"><span data-stu-id="f479f-110">The term `service worker`.</span></span>  
*   <span data-ttu-id="f479f-111">ネットワーク ツール **フィルターの** 一部 (例: `URL` , , , `XHR` `JS` `CSS` .</span><span class="sxs-lookup"><span data-stu-id="f479f-111">Some of the **Network** tool filters such as `URL`, `XHR`, `JS`, and `CSS`.</span></span>  
*   <span data-ttu-id="f479f-112">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]コンソール ユーティリティ API。</span><span class="sxs-lookup"><span data-stu-id="f479f-112">The [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] Console Utilities API.</span></span>  
    
<span data-ttu-id="f479f-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]は、ローカライズされた[](/microsoft-edge/devtools-guide-chromium/console/index.md)バージョンの DevTools のユーザーがコンソールで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f479f-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] is now available in the [Console](/microsoft-edge/devtools-guide-chromium/console/index.md) for users on localized versions of the DevTools.</span></span>   <span data-ttu-id="f479f-114">Microsoft Edge DevTools のローカライズの改善に役立つグローバル開発者コミュニティに感謝します。</span><span class="sxs-lookup"><span data-stu-id="f479f-114">Thank you to the global developer community for helping improve localization of the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="f479f-115">すべてのローカライズ [での DevTools のサポートを](#getting-in-touch-with-microsoft-edge-devtools-team) 向上させるために、ローカライズ品質に関するフィードバックを引き続き送信します。</span><span class="sxs-lookup"><span data-stu-id="f479f-115">Continue to [send feedback on localization quality](#getting-in-touch-with-microsoft-edge-devtools-team) to improve support for DevTools in all locales.</span></span>  <span data-ttu-id="f479f-116">Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#1136655。][CR1136655]</span><span class="sxs-lookup"><span data-stu-id="f479f-116">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="ローカライズされていないフィルターを含むネットワーク ツール" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   <span data-ttu-id="f479f-118">**ローカライズ** されていないフィルターを含むネットワーク ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f479f-118">**Network** pane with non-localized filters</span></span>  
:::image-end:::  

## <span data-ttu-id="f479f-119">上部と下部のパネル間でツールを移動する</span><span class="sxs-lookup"><span data-stu-id="f479f-119">Move tools between top and bottom panels</span></span>  

<span data-ttu-id="f479f-120">DevTools では、上部と下部のパネル間でのツールの移動がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f479f-120">DevTools now supports moving tools between the top and bottom panels.</span></span>  <span data-ttu-id="f479f-121">2 つのツールの任意の組み合わせを同時に表示して、DevTools をカスタマイズし、生産性を向上させます。</span><span class="sxs-lookup"><span data-stu-id="f479f-121">Customize your DevTools and improve your productivity by viewing any combination of two tools at the same time.</span></span>  <span data-ttu-id="f479f-122">たとえば、要素**ツールとソース**ツール\*\*\*\* を同時に表示します **(Sources**ツールを一番下に移動します\)。</span><span class="sxs-lookup"><span data-stu-id="f479f-122">For example, view the **Elements** and the **Sources** tools at the same time \(by moving the **Sources** tool to the bottom\).</span></span>  <span data-ttu-id="f479f-123">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue #1075732] [に移動します][CR1075732]。</span><span class="sxs-lookup"><span data-stu-id="f479f-123">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1075732][CR1075732].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="f479f-124">上部のツールを下部に移動するには、タブをポイントし、コンテキスト メニュー \(右クリック\) を開き、[下へ移動] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f479f-124">To move any top tool to the bottom, hover on a tab, open the contextual menu \(right-click\), and choose **Move to bottom**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="下に移動" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         <span data-ttu-id="f479f-126">下に移動</span><span class="sxs-lookup"><span data-stu-id="f479f-126">Move to bottom</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f479f-127">一番下のツールを一番上に移動するには、タブをポイントし、コンテキスト メニュー \(右クリック\) を開き、[上へ移動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f479f-127">To move any bottom tool to the top, hover on a tab, open the contextual menu \(right-click\), and choose **Move to top**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="上へ移動" lightbox="../../media/2020/10/move-to-top.msft.png":::
         <span data-ttu-id="f479f-129">上へ移動</span><span class="sxs-lookup"><span data-stu-id="f479f-129">Move to top</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## <span data-ttu-id="f479f-130">ネットワーク コンソールを使用して保存およびエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f479f-130">Save and export using the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="f479f-132">試験的機能</span><span class="sxs-lookup"><span data-stu-id="f479f-132">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f479f-133">ネットワーク **コンソール ツール** では [、Postman v2.1][PostmanSchemaJsonCollectionv210Index] および [OpenAPI v2][SwaggerSpecificationV2] スキーマとの互換性が向上しました。</span><span class="sxs-lookup"><span data-stu-id="f479f-133">The **Network Console** tool now has improved compatibility with the [Postman v2.1][PostmanSchemaJsonCollectionv210Index] and [OpenAPI v2][SwaggerSpecificationV2] schemas.</span></span>  <span data-ttu-id="f479f-134">実験を有効にするには、[試験的[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]な機能を有効にする] に移動し、[ネットワーク コンソールを有効にする] の横にある**チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="f479f-134">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Network Console**.</span></span>  <span data-ttu-id="f479f-135">ネットワーク コンソールの詳細については、「ネットワーク コンソール **の**試験的機能を有効 [にする」に移動します][DevtoolsExperimentalFeaturesEnableNetworkConsole]。</span><span class="sxs-lookup"><span data-stu-id="f479f-135">For more information about the **Network Console**, navigate to [Enable Network Console Experimental feature][DevtoolsExperimentalFeaturesEnableNetworkConsole].</span></span>  <span data-ttu-id="f479f-136">この実験では、次の操作がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f479f-136">This experiment now supports the following actions.</span></span>  

*   <span data-ttu-id="f479f-137">コレクションと環境を保存およびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="f479f-137">Save and export Collections and Environments.</span></span>  
*   <span data-ttu-id="f479f-138">ネットワーク コンソール ツール内の環境変数のセットを **編集およびエクスポート** します。</span><span class="sxs-lookup"><span data-stu-id="f479f-138">Edit and export sets of environment variables within the **Network Console** tool.</span></span>  
    
<span data-ttu-id="f479f-139">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページ[#1093687。][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="f479f-139">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1093687][CR1093687].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="新しい環境の名前を入力します。" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         <span data-ttu-id="f479f-141">新しい環境の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f479f-141">Enter name for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="新しい環境の形式を選択する" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         <span data-ttu-id="f479f-143">新しい環境の形式を選択する</span><span class="sxs-lookup"><span data-stu-id="f479f-143">Choose format for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="f479f-144">CSS グリッド ツールの強化</span><span class="sxs-lookup"><span data-stu-id="f479f-144">Improved CSS Grid tooling</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="f479f-146">試験的機能</span><span class="sxs-lookup"><span data-stu-id="f479f-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f479f-147">Microsoft Edge DevTools では、CSS グリッドを検査、表示、デバッグするために次の機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f479f-147">The Microsoft Edge DevTools now support the following features for inspecting, viewing, and debugging your CSS grids.</span></span>  

*   <span data-ttu-id="f479f-148">**検査**ツールを使用して、簡略化されたグリッド オーバーレイを表示するか、永続的なオーバーレイを使用してより詳細な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="f479f-148">Display a simplified grid overlay using the **Inspect** tool, or get more detailed information with persistent overlays.</span></span>  
*   <span data-ttu-id="f479f-149">固定グリッド オーバーレイを有効にするには、 **要素** ツールのグリッド コンテナー要素の横にあるグリッド アイコンを選択するか、レイアウト ツールでグリッドを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="f479f-149">To enable persistent grid overlays, choose the grid icon next to a grid container element in the **Elements** tool or choose the grid in the **Layout** tool.</span></span>  
*   <span data-ttu-id="f479f-150">複数のグリッドに対して固定オーバーレイを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f479f-150">You may enable persistent overlays for multiple grids.</span></span>  
*   <span data-ttu-id="f479f-151">新しい **レイアウト ツールを** 使用すると、グリッド オーバーレイを簡単に切り替え、それぞれの外観とコンテンツを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f479f-151">The new **Layout** tool allows you to easily toggle grid overlays and configure the appearance and the content for each.</span></span>  
    
<span data-ttu-id="f479f-152">この機能は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f479f-152">The features are turned on by default.</span></span>  <span data-ttu-id="f479f-153">機能の詳細については [、CSS グリッドに移動します][DevtoolsCssGrid]。</span><span class="sxs-lookup"><span data-stu-id="f479f-153">For more information about the features, navigate to [CSS grids][DevtoolsCssGrid].</span></span>  <span data-ttu-id="f479f-154">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue #1047356] [に移動します][CR1047356]。</span><span class="sxs-lookup"><span data-stu-id="f479f-154">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1047356][CR1047356].</span></span>  <span data-ttu-id="f479f-155">さらに、Microsoft Edge DevTools チームは Chrome DevTools チームおよび Chromium コミュニティと協力して、DevTools に新しい flexbox ツール機能を追加しています。</span><span class="sxs-lookup"><span data-stu-id="f479f-155">Additionally, the Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new flexbox tooling features to DevTools.</span></span>  <span data-ttu-id="f479f-156">Chromium オープン ソース プロジェクトの flexbox ツールの更新については、[問題] ページ[#1136394。][CR1136394]</span><span class="sxs-lookup"><span data-stu-id="f479f-156">For updates on flexbox tooling in the Chromium open-source project, navigate to Issue [#1136394][CR1136394].</span></span>  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="グリッドを含むレイアウト ツール" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   <span data-ttu-id="f479f-158">**グリッド** を含むレイアウト ツール</span><span class="sxs-lookup"><span data-stu-id="f479f-158">**Layout** tool with grids</span></span>  
:::image-end:::  

## <span data-ttu-id="f479f-159">[設定] でキーボード ショートカットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="f479f-159">Customize keyboard shortcuts in Settings</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="f479f-161">試験的機能</span><span class="sxs-lookup"><span data-stu-id="f479f-161">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f479f-162">これで、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f479f-162">You are now able to customize the keyboard shortcut for any action in the DevTools.</span></span>  <span data-ttu-id="f479f-163">Microsoft Edge バージョン 84 以降では、キーボード ショートカットの既定の Visual Studio **コード** と **DevTools (既定)** のプリセットから [選択できます][DevtoolsCustomizeShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="f479f-163">Since Microsoft Edge version 84, you are able to choose between **Visual Studio Code** and **DevTools (default)** presets for [keyboard shortcuts][DevtoolsCustomizeShortcuts].</span></span>  <span data-ttu-id="f479f-164">Microsoft Edge バージョン 87 から、キーボード ショートカット\*\*\*\* エディターの有効化実験を有効にして、キーボード ショートカットをさらに[カスタマイズできます][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="f479f-164">Starting in Microsoft Edge version 87, you may turn on the **Enable keyboard shortcut editor** experiment to further [customize keyboard shortcuts][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="f479f-165">実験を有効にするには、[試験的[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]な機能を有効にする] に移動し、[キーボード ショートカット エディターを有効にする] の横にあるチェック**ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="f479f-165">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="f479f-166">ショートカットのカスタマイズと編集の詳細については、「[キーボード ショートカット エディターの試験的機能を有効にする][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="f479f-166">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  <span data-ttu-id="f479f-167">Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#174309。][CR174309]</span><span class="sxs-lookup"><span data-stu-id="f479f-167">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="スクリプトを一時停止するカスタム ショートカット" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   <span data-ttu-id="f479f-169">スクリプトを一時停止するカスタム ショートカット</span><span class="sxs-lookup"><span data-stu-id="f479f-169">Custom shortcut for pausing a script</span></span>  
:::image-end:::  

## <span data-ttu-id="f479f-170">Microsoft Edge Tools for Visual Studio Code 拡張機能の紹介</span><span class="sxs-lookup"><span data-stu-id="f479f-170">Introducing the Microsoft Edge Tools for Visual Studio Code extension</span></span>  

<span data-ttu-id="f479f-171">現在 **、Visual Studio Code** 拡張機能と **Network for Visual Studio コード** 拡張機能の要素は、新しい [Microsoft Edge Developer Tools for Visual Studio統合][VisualStudioCodeMarketplaceMsEdgedevtools] されました。</span><span class="sxs-lookup"><span data-stu-id="f479f-171">The **Elements for Visual Studio Code** and **Network for Visual Studio Code** extensions are now merged into the new [Microsoft Edge Developer Tools for Visual Studio Code][VisualStudioCodeMarketplaceMsEdgedevtools] extension.</span></span>  <span data-ttu-id="f479f-172">Microsoft Edge DevTools は、次のコードを残さずに次のVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="f479f-172">Use the Microsoft Edge DevTools for the following activities without leaving Visual Studio Code.</span></span>  

*   <span data-ttu-id="f479f-173">DOM をデバッグする</span><span class="sxs-lookup"><span data-stu-id="f479f-173">Debug the DOM</span></span>  
*   <span data-ttu-id="f479f-174">CSS の編集</span><span class="sxs-lookup"><span data-stu-id="f479f-174">Edit CSS</span></span>  
*   <span data-ttu-id="f479f-175">ネットワーク トラフィックを検査する</span><span class="sxs-lookup"><span data-stu-id="f479f-175">Inspect network traffic</span></span>  

<span data-ttu-id="f479f-176">拡張機能を使用して、Microsoft Edge を起動するか、ブラウザーの既存のインスタンスに接続するか、エディターから直接ヘッドレス ブラウザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f479f-176">With the extension, launch Microsoft Edge, connect to an existing instance of the browser, or use a headless browser directly from your editor.</span></span>  <span data-ttu-id="f479f-177">この拡張機能に関するフィードバックに関する問題の提出と提出を開始するには、GitHub の [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] リポジトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f479f-177">To start contributing and filing issues with your feedback about this extension, navigate to the [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] repo on GitHub.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="ブラウザー モードの完全なスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         <span data-ttu-id="f479f-179">ブラウザー モードの完全なスクリーンショットで拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="f479f-179">Using the extension in full browser mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="ヘッドレス モードでの拡張機能の使用のスクリーンショット" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         <span data-ttu-id="f479f-181">ヘッドレス モードでの拡張機能の使用のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="f479f-181">Using the extension in headless mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="f479f-182">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="f479f-182">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="f479f-183">新しい WebAuthn ツール</span><span class="sxs-lookup"><span data-stu-id="f479f-183">New WebAuthn tool</span></span>  

<span data-ttu-id="f479f-184">以前のバージョンの Microsoft Edge では、ネイティブの WebAuthn デバッグサポートは提供されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="f479f-184">In earlier versions of Microsoft Edge, there was no native WebAuthn debugging support.</span></span>  <span data-ttu-id="f479f-185">Web 認証 API を使用して Web アプリケーションをテストするには、物理認証システム [が必要でした][GithubW3cWebauthn]。</span><span class="sxs-lookup"><span data-stu-id="f479f-185">You needed physical authenticators to test your web application with the [Web Authentication API][GithubW3cWebauthn].</span></span>  <span data-ttu-id="f479f-186">新しい **WebAuthn** ツールを使用すると、物理認証を使用せずに次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f479f-186">With the new **WebAuthn** tool, you are able to do the following actions without the use of any physical authenticators.</span></span>

*   <span data-ttu-id="f479f-187">認証システムをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="f479f-187">Emulate authenticators</span></span>
*   <span data-ttu-id="f479f-188">認証システムの属性をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="f479f-188">Customize attributes of authenticators</span></span>
*   <span data-ttu-id="f479f-189">認証システムの状態を検査する</span><span class="sxs-lookup"><span data-stu-id="f479f-189">Inspect states of authenticators</span></span>
    
<span data-ttu-id="f479f-190">WebAuthn 機能の詳細 **については、「Authenticators** をエミュレートする」に移動し [、Microsoft Edge DevTools で WebAuthn をデバッグします][DevtoolsWebauthnIndex]。</span><span class="sxs-lookup"><span data-stu-id="f479f-190">For more information about the **WebAuthn** feature, navigate to [Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools][DevtoolsWebauthnIndex].</span></span>  

<span data-ttu-id="f479f-191">新しい[WebAuthn][DevtoolsWebauthnIndex]ツールを使用して、認証機能をエミュレートし、Web 認証[API][GithubW3cWebauthn]をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="f479f-191">You are able to emulate authenticators and debug the [Web Authentication API][GithubW3cWebauthn] with the new [WebAuthn][DevtoolsWebauthnIndex] tool.</span></span>  <span data-ttu-id="f479f-192">**WebAuthn ツールを開**するには **、[DevTools**のカスタマイズと制御] アイコン (\) アイコンを選択し、[ `...` その他> \*\*\*\*  >  **WebAuthn] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f479f-192">To open the **WebAuthn** tool, choose **the Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  <span data-ttu-id="f479f-193">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページ[#1034663。][CR1034663]</span><span class="sxs-lookup"><span data-stu-id="f479f-193">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1034663][CR1034663].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="WebAuthn ツールを開く" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         <span data-ttu-id="f479f-195">**WebAuthn ツールを開**く</span><span class="sxs-lookup"><span data-stu-id="f479f-195">Open the **WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn ツール" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         <span data-ttu-id="f479f-197">**WebAuthn** ツール</span><span class="sxs-lookup"><span data-stu-id="f479f-197">**WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="f479f-198">要素ツールの更新</span><span class="sxs-lookup"><span data-stu-id="f479f-198">Elements tool updates</span></span>  

#### <span data-ttu-id="f479f-199">[スタイル] ウィンドウの [計算されたサイドバー] ウィンドウを表示する</span><span class="sxs-lookup"><span data-stu-id="f479f-199">View the Computed sidebar pane in the Styles pane</span></span>  

<span data-ttu-id="f479f-200">[スタイル **] ウィンドウの [** 計算] ウィンドウ **を切り替** えます。</span><span class="sxs-lookup"><span data-stu-id="f479f-200">Toggle the **Computed** pane in the **Styles** pane.</span></span>  <span data-ttu-id="f479f-201">[ **スタイル] ウィンドウ** の [ **計算** ] ウィンドウは、既定で折りたたまれています。</span><span class="sxs-lookup"><span data-stu-id="f479f-201">The **Computed** pane in the **Styles** pane is collapsed by default.</span></span>  <span data-ttu-id="f479f-202">切り替えるには、ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f479f-202">To toggle it, choose the button.</span></span>  <span data-ttu-id="f479f-203">Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#1073899。][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="f479f-203">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1073899][CR1073899].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="計算されたサイドバー ウィンドウを開く" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         <span data-ttu-id="f479f-205">計算された **サイドバー ウィンドウを開** く</span><span class="sxs-lookup"><span data-stu-id="f479f-205">Open the **Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="計算されたサイドバー ウィンドウ" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         <span data-ttu-id="f479f-207">**計算されたサイドバー** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f479f-207">**Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="f479f-208">計算パネルでの CSS プロパティのグループ化</span><span class="sxs-lookup"><span data-stu-id="f479f-208">Grouping CSS properties in the Computed panel</span></span>  

<span data-ttu-id="f479f-209">適用されている CSS のスクロールを減らして表示するには、[計算] ウィンドウで CSS プロパティをカテゴリ別 **にグループ化** します。</span><span class="sxs-lookup"><span data-stu-id="f479f-209">To view your applied CSS with less scrolling, group the CSS properties by categories in the **Computed** pane.</span></span>  <span data-ttu-id="f479f-210">また、CSS を検査する間は、関連するプロパティのセットに選択的に焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f479f-210">You may also selectively focus on a set of related properties while you inspect your CSS.</span></span>  <span data-ttu-id="f479f-211">要素ツール **から** 要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="f479f-211">From the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="f479f-212">CSS プロパティを \(または ungroup\) グループ化するには、[グループ] チェック ボックスを **オフ** にします。</span><span class="sxs-lookup"><span data-stu-id="f479f-212">To group \(or ungroup\) the CSS properties, toggle the **Group** checkbox.</span></span>  <span data-ttu-id="f479f-213">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] #1096230 [#1084673][CR1096230] []、][CR1084673]および [更新[#1106251。][CR1106251]</span><span class="sxs-lookup"><span data-stu-id="f479f-213">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1096230][CR1096230], [#1084673][CR1084673], and [#1106251][CR1106251].</span></span>  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="CSS プロパティのグループ化" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   <span data-ttu-id="f479f-215">CSS プロパティのグループ化</span><span class="sxs-lookup"><span data-stu-id="f479f-215">Grouping CSS properties</span></span>  
:::image-end:::  

### <span data-ttu-id="f479f-216">1 つ以上のツールの 6.4</span><span class="sxs-lookup"><span data-stu-id="f479f-216">Lighthouse 6.4 in the Lighthouse tool</span></span>  

<span data-ttu-id="f479f-217">これで **、The 立** ち回りツールは 6.4 を実行しています。</span><span class="sxs-lookup"><span data-stu-id="f479f-217">The **Lighthouse** tool is now running Lighthouse 6.4.</span></span>  <span data-ttu-id="f479f-218">変更の完全な一覧については、大島のリリース [ノートに移動します][GithubGoogleChromeLighthouseReleasesV641]。</span><span class="sxs-lookup"><span data-stu-id="f479f-218">For a full list of changes, navigate to the [Lighthouse release notes][GithubGoogleChromeLighthouseReleasesV641].</span></span>  <span data-ttu-id="f479f-219">Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#772558。][CR772558]</span><span class="sxs-lookup"><span data-stu-id="f479f-219">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#772558][CR772558].</span></span>  

### <span data-ttu-id="f479f-220">[タイミング] セクションの performance.mark() イベント</span><span class="sxs-lookup"><span data-stu-id="f479f-220">performance.mark() events in the Timings section</span></span>  

<span data-ttu-id="f479f-221">パフォーマンス **ツールの記録の** [タイミング] セクション [でイベントが][DevtoolsGuideChromiumEvaluatePerformanceReference] マーク `performance.mark()` されます。</span><span class="sxs-lookup"><span data-stu-id="f479f-221">The **Timings section** of a recording in the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool now marks `performance.mark()` events.</span></span>  <span data-ttu-id="f479f-222">この機能を試し、JavaScript コードのパフォーマンスを測定するには、コード `performance.mark()` にイベントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f479f-222">To try this feature and measure the performance of your JavaScript code, add `performance.mark()` events to your code.</span></span>  <span data-ttu-id="f479f-223">たとえば、次のコード スニペットでは、ループの前と後にマーカーを追加し、7 の増分を使用して 0 から `for` 1000 まで反復します。</span><span class="sxs-lookup"><span data-stu-id="f479f-223">For example, the following code snippet adds markers before and after a `for` loop that iterates from 0 to 1000 using increments of 7.</span></span>  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

<span data-ttu-id="f479f-224">次に、パフォーマンス ツール [を開][DevtoolsGuideChromiumEvaluatePerformanceReference] き、[ **タイミング]** セクションに移動して JavaScript コードを記録します。</span><span class="sxs-lookup"><span data-stu-id="f479f-224">Then, open the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool and navigate to the **Timings section** to record your JavaScript code.</span></span>  <span data-ttu-id="f479f-225">追加 `performance.mark()` したイベントが記録に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f479f-225">The `performance.mark()` events you added are now displayed in the recording.</span></span>  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="Performance.mark イベント" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` <span data-ttu-id="f479f-227">events</span><span class="sxs-lookup"><span data-stu-id="f479f-227">events</span></span>  
:::image-end:::  

### <span data-ttu-id="f479f-228">ネットワーク ツールの新しいリソースの種類と URL フィルター</span><span class="sxs-lookup"><span data-stu-id="f479f-228">New resource-type and url filters in the Network tool</span></span>  

<span data-ttu-id="f479f-229">ネットワーク ツールの `resource-type` 新 `url` しいキーワードを\*\*\*\* 使用して、ネットワーク要求をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f479f-229">Use the new `resource-type` and `url` keywords in the **Network** tool to filter network requests.</span></span>  <span data-ttu-id="f479f-230">たとえば、画像 `resource-type:image` であるネットワーク要求に焦点を当てる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f479f-230">For example, use `resource-type:image` to focus on the network requests that are images.</span></span>  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="resource-type filter" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   <span data-ttu-id="f479f-232">resource-type filter</span><span class="sxs-lookup"><span data-stu-id="f479f-232">resource-type filter</span></span>  
:::image-end:::  

<span data-ttu-id="f479f-233">To discover more special keywords such as `resource-type` `url` and, navigate to [filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties].</span><span class="sxs-lookup"><span data-stu-id="f479f-233">To discover more special keywords such as `resource-type` and `url`, navigate to [filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties].</span></span>  <span data-ttu-id="f479f-234">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題] [#1121141に移動][CR1121141]して[#1104188。][CR1104188]</span><span class="sxs-lookup"><span data-stu-id="f479f-234">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1121141][CR1121141] and [#1104188][CR1104188].</span></span>  

### <span data-ttu-id="f479f-235">フレーム詳細ビューの更新</span><span class="sxs-lookup"><span data-stu-id="f479f-235">Frame details view updates</span></span>  

#### <span data-ttu-id="f479f-236">COEP および COOP レポートをエンドポイントに表示する</span><span class="sxs-lookup"><span data-stu-id="f479f-236">Display COEP and COOP reporting to endpoint</span></span>  

<span data-ttu-id="f479f-237">[セキュリティと保護の分離] セクションで、クロスオリジン 埋め込みポリシー \(COEP\) およびクロスオリジン オープン ポリシー \(COOP\) `reporting to` **エンドポイント&表示** します。</span><span class="sxs-lookup"><span data-stu-id="f479f-237">View the Cross-Origin Embedder Policy \(COEP\) and Cross-Origin Opener Policy \(COOP\) `reporting to` endpoint under the **Security & Isolation** section.</span></span>  <span data-ttu-id="f479f-238">レポート [API は][MdnReportingApi] 、新しい HTTP ヘッダーを定義します。これにより、ブラウザーが警告やエラーを送信するためのサーバー エンドポイント `Report-To` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f479f-238">The [Reporting API][MdnReportingApi] defines `Report-To`, a new HTTP header, that gives you a way to specify the server endpoints for the browser to send warnings and errors.</span></span>  <span data-ttu-id="f479f-239">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページに移動[#1051466。][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="f479f-239">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="エンドポイントへのレポート" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   <span data-ttu-id="f479f-241">エンドポイント `reporting to`</span><span class="sxs-lookup"><span data-stu-id="f479f-241">The `reporting to` endpoint</span></span>  
:::image-end:::  

#### <span data-ttu-id="f479f-242">COEP および COOP レポート専用モードを表示する</span><span class="sxs-lookup"><span data-stu-id="f479f-242">Display COEP and COOP report-only mode</span></span>  

<span data-ttu-id="f479f-243">DevTools に、モードに `report-only` 設定されている COEP と COOP のラベルが表示 `report-only` されます。</span><span class="sxs-lookup"><span data-stu-id="f479f-243">DevTools now display the `report-only` label for COEP and COOP that are set to `report-only` mode.</span></span>  <span data-ttu-id="f479f-244">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページに移動[#1051466。][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="f479f-244">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="レポート専用モード ラベル" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   <span data-ttu-id="f479f-246">モード `report-only` ラベル</span><span class="sxs-lookup"><span data-stu-id="f479f-246">The `report-only` mode label</span></span>  
:::image-end:::  

### <span data-ttu-id="f479f-247">CSS 概要ツールで色コントラストの問題を表示および修正する</span><span class="sxs-lookup"><span data-stu-id="f479f-247">View and fix color contrast issues in the CSS Overview tool</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="f479f-249">試験的機能</span><span class="sxs-lookup"><span data-stu-id="f479f-249">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f479f-250">CSS **概要ツールで** 、ページ上に色コントラストの問題がある要素の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f479f-250">The **CSS Overview** tool now displays a list of elements on your page that have color contrast issues.</span></span>  <span data-ttu-id="f479f-251">次のデモ ページには、カラー コントラストの問題の例が示されています。</span><span class="sxs-lookup"><span data-stu-id="f479f-251">The following demo page has an example of a color contrast issue.</span></span>  

[<span data-ttu-id="f479f-252">CSS の概要のアクセス可能な色のデモ</span><span class="sxs-lookup"><span data-stu-id="f479f-252">CSS Overview Accessible Colors Demo</span></span>][GlitchCssOverviewAccessibleColorsDemo]  

<span data-ttu-id="f479f-253">この実験を有効にするには、[設定**の実験]**  >  **で**、[CSS の概要]**チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="f479f-253">To enable this experiment, under **Settings** > **Experiments**, choose the **CSS Overview** checkbox.</span></span>  <span data-ttu-id="f479f-254">色コントラストの問題がある要素の一覧を表示するには、[ **コントラスト**] の問題で [テキスト] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="f479f-254">To view a list of elements that have a color contrast issue, on **Contrast issues**, choose **Text**.</span></span>  <span data-ttu-id="f479f-255">要素ツールで要素を **開く** 場合は、一覧から要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="f479f-255">To open the element in the **Elements** tool, choose an element in the list.</span></span>  <span data-ttu-id="f479f-256">コントラストの問題を解決するために、Microsoft Edge DevTools は自動的に色の候補 [を提供します][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。</span><span class="sxs-lookup"><span data-stu-id="f479f-256">To help fix contrast issues, the Microsoft Edge DevTools [automatically provide color suggestions][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane].</span></span>  <span data-ttu-id="f479f-257">Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#1120316。][CR1120316]</span><span class="sxs-lookup"><span data-stu-id="f479f-257">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1120316][CR1120316].</span></span>  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低色コントラストの問題" lightbox="../../media/2020/10/css-overview.msft.png":::
   <span data-ttu-id="f479f-259">低色コントラストの問題</span><span class="sxs-lookup"><span data-stu-id="f479f-259">Low color contrast issues</span></span>  
:::image-end:::  

## <span data-ttu-id="f479f-260">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f479f-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="f479f-261">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f479f-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="f479f-262">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f479f-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="f479f-263">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="f479f-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "Elements ツールの [プロパティ] ウィンドウの廃止 - DevTools (Microsoft Edge 84) の新機能|Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS グリッド デバッグ機能 - DevTools の新機能 (Microsoft Edge 85) |Microsoft Docs"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane "[スタイル] ウィンドウのアクセス可能な色の候補 - DevTools の新機能 (Microsoft Edge 86) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "パフォーマンス分析のリファレンス |Microsoft Docs"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "試験的な API を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボード ショートカット エディターを有効にする - 試験的な機能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "ネットワーク コンソールを有効にする - 試験的な機能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース オーダー ビューアーを有効にする - 試験的機能 | Microsoft Docs"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式デバイスとデュアルスクリーン デバイスのテスト - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "試験的機能を有効にする - 試験的な機能|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "table - コンソール API リファレンス | Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける | Microsoft Docs"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "CSS グリッド を検査|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでレンダリング パフォーマンスを分析する - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "メディア プレーヤー情報の表示とデバッグ|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "プロパティで要求をフィルター処理する - ネットワーク分析の参照|Microsoft Docs"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "Microsoft Edge DevTools アプリケーションで認証システムをエミュレートし、WebAuthn をデバッグ|Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio コード"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium bugs"
[CR772558]: https://crbug.com/772558 "DevTools: Lighthouse の最新バージョンに更新する | Chromium bugs"  
[CR1034663]: https://crbug.com/1034663 "WebAuthn テスト API サービスのフロントエンドを作成|Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/Table ツーリング | Chromium bugs"  
[CR1051466]: https://crbug.com/1051466 "DevTools での COOP/COEP デバッグのサポート | Chromium bugs"  
[CR1073899]: https://crbug.com/1073899 "計算済みのスタイル タブが応答モードで表示されない | Chromium のバグ"  
[CR1075732]: https://crbug.com/1075732 "DevTools 個人用設定 - 移動可能なタブ |Chromium のバグ"  
[CR1084673]: https://crbug.com/1084673 "DevTools: CSS カスタム プロパティ ((aka) を表示する方法を改善します。CSS 変数) とその値|Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "統合ネットワーク要求を作成および再生するためのツールを作成する | Chromium のバグ"  
[CR1096230]: https://crbug.com/1096230 "[計算されたスタイル] ウィンドウのカテゴリ別に CSS プロパティを|Chromium のバグ"  
[CR1104188]: https://crbug.com/1104188 "完全な URL を検索しても、ネットワーク ツールの検索で結果が|Chromium のバグ"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools: [計算されたスタイル] タブの|Chromium のバグ"  
[CR1120316]: https://crbug.com/1120316 "CSS Overview > Colors |Chromium Bugs"  
[CR1121141]: https://crbug.com/1121141 "ネットワーク ログ サーバーでリソースの種類によるフィルター処理を|Chromium のバグ"  
[CR1121312]: https://crbug.com/1121312 "[その他のツール] メニューから設定を削除する必要|Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "Flexbox ツール |Chromium Bugs"  
[CR1136655]: https://crbug.com/1136655 "Devtools: ローカライズ V2 |Chromium のバグ"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "レポート API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v6.4.1 - GoogleChrome/|GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証|GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "Hello! |Glitch"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman コレクション形式 v2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 仕様|Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> <span data-ttu-id="f479f-316">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="f479f-316">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f479f-317">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/10/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="f479f-317">The original page is found [here](https://developers.google.com/web/updates/2020/10/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f479f-319">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f479f-319">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen