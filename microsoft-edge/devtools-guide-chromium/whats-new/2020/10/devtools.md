---
description: 新しい CSS Grid デバッグ ツール、Webauthn ツール、移動可能なツール、および計算されたサイドバー パネル。
title: DevTools の新機能 (Microsoft Edge 87)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 53aa8f20ba400c7ff95432b1e752f1f008dac919
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408333"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-87"></a><span data-ttu-id="b5b56-104">DevTools の新機能 (Microsoft Edge 87)</span><span class="sxs-lookup"><span data-stu-id="b5b56-104">What's New In DevTools (Microsoft Edge 87)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="improving-devtools-localization"></a><span data-ttu-id="b5b56-105">DevTools ローカライズの改善</span><span class="sxs-lookup"><span data-stu-id="b5b56-105">Improving DevTools localization</span></span>  

<span data-ttu-id="b5b56-106">Microsoft Edge DevTools チームは、翻訳のニーズを満たすために、翻訳品質の向上に重点を置いてみることができます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-106">To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.</span></span>  <span data-ttu-id="b5b56-107">Microsoft Edge バージョン 87 から、いくつかの文字列と用語がロックされ、残りの DevTools が他の言語で表示されている場合でも変更されません。</span><span class="sxs-lookup"><span data-stu-id="b5b56-107">Starting in Microsoft Edge version 87, several strings and terms are locked and do not change even when the rest of the DevTools are displayed in other languages.</span></span>  <span data-ttu-id="b5b56-108">影響を受ける文字列と用語の一覧には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-108">The list of affected strings and terms include the following.</span></span>  

*   <span data-ttu-id="b5b56-109">ライトハウス ツール **の** 文字列。</span><span class="sxs-lookup"><span data-stu-id="b5b56-109">The strings in the **Lighthouse** tool.</span></span>  
*   <span data-ttu-id="b5b56-110">用語 `service worker` .</span><span class="sxs-lookup"><span data-stu-id="b5b56-110">The term `service worker`.</span></span>  
*   <span data-ttu-id="b5b56-111">ネットワーク ツールの **フィルターの** 一部 `URL` `XHR` (、、、 `JS` `CSS` など)。</span><span class="sxs-lookup"><span data-stu-id="b5b56-111">Some of the **Network** tool filters such as `URL`, `XHR`, `JS`, and `CSS`.</span></span>  
*   <span data-ttu-id="b5b56-112">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]コンソール ユーティリティ API。</span><span class="sxs-lookup"><span data-stu-id="b5b56-112">The [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] Console Utilities API.</span></span>  
    
<span data-ttu-id="b5b56-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]は、ローカライズされた[](/microsoft-edge/devtools-guide-chromium/console/index.md)バージョンの DevTools のユーザーがコンソールで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] is now available in the [Console](/microsoft-edge/devtools-guide-chromium/console/index.md) for users on localized versions of the DevTools.</span></span>   <span data-ttu-id="b5b56-114">Microsoft Edge DevTools のローカライズの改善に役立つグローバル開発者コミュニティに感謝します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-114">Thank you to the global developer community for helping improve localization of the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="b5b56-115">すべての地域 [での DevTools](#getting-in-touch-with-microsoft-edge-devtools-team) のサポートを向上させるために、ローカライズ品質に関するフィードバックを引き続き送信します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-115">Continue to [send feedback on localization quality](#getting-in-touch-with-microsoft-edge-devtools-team) to improve support for DevTools in all locales.</span></span>  <span data-ttu-id="b5b56-116">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[問題の修正] に[#1136655。][CR1136655]</span><span class="sxs-lookup"><span data-stu-id="b5b56-116">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="ローカライズされていないフィルターを含むネットワーク ツール" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   <span data-ttu-id="b5b56-118">**ローカライズ** されていないフィルターを含むネットワーク ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b5b56-118">**Network** pane with non-localized filters</span></span>  
:::image-end:::  

## <a name="move-tools-between-top-and-bottom-panels"></a><span data-ttu-id="b5b56-119">上部パネルと下部パネルの間でツールを移動する</span><span class="sxs-lookup"><span data-stu-id="b5b56-119">Move tools between top and bottom panels</span></span>  

<span data-ttu-id="b5b56-120">DevTools では、上部パネルと下部パネルの間でのツールの移動がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-120">DevTools now supports moving tools between the top and bottom panels.</span></span>  <span data-ttu-id="b5b56-121">2 つのツールの任意の組み合わせを同時に表示することで、DevTools をカスタマイズし、生産性を向上させます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-121">Customize your DevTools and improve your productivity by viewing any combination of two tools at the same time.</span></span>  <span data-ttu-id="b5b56-122">たとえば、[要素] ツールと\*\*\*\*\*\*[\*\* ソース] ツールを同時に表示します ([ソース] ツールを下部\に移動します)。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b5b56-122">For example, view the **Elements** and the **Sources** tools at the same time \(by moving the **Sources** tool to the bottom\).</span></span>  <span data-ttu-id="b5b56-123">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[問題の修正] に[#1075732。][CR1075732]</span><span class="sxs-lookup"><span data-stu-id="b5b56-123">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1075732][CR1075732].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="b5b56-124">上部のツールを下部に移動するには、タブにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[下へ移動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5b56-124">To move any top tool to the bottom, hover on a tab, open the contextual menu \(right-click\), and choose **Move to bottom**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="下に移動する" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         <span data-ttu-id="b5b56-126">下に移動する</span><span class="sxs-lookup"><span data-stu-id="b5b56-126">Move to bottom</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="b5b56-127">下部ツールを上部に移動するには、タブにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[上へ移動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5b56-127">To move any bottom tool to the top, hover on a tab, open the contextual menu \(right-click\), and choose **Move to top**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="上に移動する" lightbox="../../media/2020/10/move-to-top.msft.png":::
         <span data-ttu-id="b5b56-129">上に移動する</span><span class="sxs-lookup"><span data-stu-id="b5b56-129">Move to top</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## <a name="save-and-export-using-the-network-console"></a><span data-ttu-id="b5b56-130">ネットワーク コンソールを使用して保存およびエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b5b56-130">Save and export using the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="b5b56-132">試験的機能</span><span class="sxs-lookup"><span data-stu-id="b5b56-132">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="b5b56-133">ネットワーク **コンソール ツール** は、Postman [v2.1][PostmanSchemaJsonCollectionv210Index] および [OpenAPI v2][SwaggerSpecificationV2] スキーマとの互換性を向上しました。</span><span class="sxs-lookup"><span data-stu-id="b5b56-133">The **Network Console** tool now has improved compatibility with the [Postman v2.1][PostmanSchemaJsonCollectionv210Index] and [OpenAPI v2][SwaggerSpecificationV2] schemas.</span></span>  <span data-ttu-id="b5b56-134">実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]を有効にする] に移動し、[ネットワーク コンソールを有効にする] の横にある**チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="b5b56-134">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Network Console**.</span></span>  <span data-ttu-id="b5b56-135">ネットワーク コンソールの詳細については、「 **ネットワーク**コンソールの実験機能を有効 [にする」に移動します][DevtoolsExperimentalFeaturesEnableNetworkConsole]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-135">For more information about the **Network Console**, navigate to [Enable Network Console Experimental feature][DevtoolsExperimentalFeaturesEnableNetworkConsole].</span></span>  <span data-ttu-id="b5b56-136">この実験では、次のアクションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-136">This experiment now supports the following actions.</span></span>  

*   <span data-ttu-id="b5b56-137">コレクションと環境を保存およびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b5b56-137">Save and export Collections and Environments.</span></span>  
*   <span data-ttu-id="b5b56-138">ネットワーク コンソール ツール内の環境変数のセットを **編集およびエクスポート** します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-138">Edit and export sets of environment variables within the **Network Console** tool.</span></span>  
    
<span data-ttu-id="b5b56-139">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[問題の修正] に[#1093687。][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="b5b56-139">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1093687][CR1093687].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="新しい環境の名前を入力する" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         <span data-ttu-id="b5b56-141">新しい環境の名前を入力する</span><span class="sxs-lookup"><span data-stu-id="b5b56-141">Enter name for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="新しい環境の形式を選択する" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         <span data-ttu-id="b5b56-143">新しい環境の形式を選択する</span><span class="sxs-lookup"><span data-stu-id="b5b56-143">Choose format for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-grid-tooling"></a><span data-ttu-id="b5b56-144">CSS グリッド ツールの改善</span><span class="sxs-lookup"><span data-stu-id="b5b56-144">Improved CSS Grid tooling</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="b5b56-146">試験的機能</span><span class="sxs-lookup"><span data-stu-id="b5b56-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="b5b56-147">Microsoft Edge DevTools では、CSS グリッドの検査、表示、およびデバッグを行う次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-147">The Microsoft Edge DevTools now support the following features for inspecting, viewing, and debugging your CSS grids.</span></span>  

*   <span data-ttu-id="b5b56-148">[検査] ツールを使用して簡略化されたグリッド **オーバーレイを表示** するか、永続的なオーバーレイを使用して詳細な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-148">Display a simplified grid overlay using the **Inspect** tool, or get more detailed information with persistent overlays.</span></span>  
*   <span data-ttu-id="b5b56-149">永続的なグリッド オーバーレイを有効にするには、[要素] ツールでグリッド コンテナー要素の\*\*\*\* 横にあるグリッド アイコンを選択するか、レイアウト ツールでグリッドを**選択**します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-149">To enable persistent grid overlays, choose the grid icon next to a grid container element in the **Elements** tool or choose the grid in the **Layout** tool.</span></span>  
*   <span data-ttu-id="b5b56-150">複数のグリッドに対して永続的なオーバーレイを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-150">You may enable persistent overlays for multiple grids.</span></span>  
*   <span data-ttu-id="b5b56-151">新しい **レイアウト ツール** を使用すると、グリッド オーバーレイを簡単に切り替え、それぞれの外観とコンテンツを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-151">The new **Layout** tool allows you to easily toggle grid overlays and configure the appearance and the content for each.</span></span>  
    
<span data-ttu-id="b5b56-152">機能は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-152">The features are turned on by default.</span></span>  <span data-ttu-id="b5b56-153">機能の詳細については [、CSS グリッドに移動します][DevtoolsCssGrid]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-153">For more information about the features, navigate to [CSS grids][DevtoolsCssGrid].</span></span>  <span data-ttu-id="b5b56-154">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[ファイルの発行] に[#1047356。][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="b5b56-154">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1047356][CR1047356].</span></span>  <span data-ttu-id="b5b56-155">さらに、Microsoft Edge DevTools チームは、Chrome DevTools チームと Chrome コミュニティと協力して、DevTools に新しいフレックスボックス ツール機能を追加しています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-155">Additionally, the Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new flexbox tooling features to DevTools.</span></span>  <span data-ttu-id="b5b56-156">Chromium オープン ソース プロジェクトのフレックスボックス ツールの更新については、[問題の修正] に[#1136394。][CR1136394]</span><span class="sxs-lookup"><span data-stu-id="b5b56-156">For updates on flexbox tooling in the Chromium open-source project, navigate to Issue [#1136394][CR1136394].</span></span>  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="グリッド付きレイアウト ツール" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   <span data-ttu-id="b5b56-158">**グリッド** 付きレイアウト ツール</span><span class="sxs-lookup"><span data-stu-id="b5b56-158">**Layout** tool with grids</span></span>  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a><span data-ttu-id="b5b56-159">[設定] でキーボード ショートカットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b5b56-159">Customize keyboard shortcuts in Settings</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="b5b56-161">試験的機能</span><span class="sxs-lookup"><span data-stu-id="b5b56-161">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="b5b56-162">これで、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-162">You are now able to customize the keyboard shortcut for any action in the DevTools.</span></span>  <span data-ttu-id="b5b56-163">Microsoft Edge バージョン 84 以降では、キーボード\*\*\*\* ショートカットの既定のコードVisual Studio **DevTools (既定)** のプリセットから[選択できます][DevtoolsCustomizeShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-163">Since Microsoft Edge version 84, you are able to choose between **Visual Studio Code** and **DevTools (default)** presets for [keyboard shortcuts][DevtoolsCustomizeShortcuts].</span></span>  <span data-ttu-id="b5b56-164">Microsoft Edge バージョン 87 から、キーボード ショートカット\*\*\*\* をさらにカスタマイズするには、[キーボード ショートカット エディターの有効化] 実験[を有効にできます][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-164">Starting in Microsoft Edge version 87, you may turn on the **Enable keyboard shortcut editor** experiment to further [customize keyboard shortcuts][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="b5b56-165">実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]を有効にする] に移動し、[キーボード ショートカット エディターを有効にする] の横にある**チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="b5b56-165">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="b5b56-166">ショートカットのカスタマイズと編集の詳細については、「[キーボード ショートカット エディターの試験的機能を有効にする][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-166">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  <span data-ttu-id="b5b56-167">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイム更新プログラムを確認するには、[問題の修正] に[#174309。][CR174309]</span><span class="sxs-lookup"><span data-stu-id="b5b56-167">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="スクリプトを一時停止するカスタム ショートカット" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   <span data-ttu-id="b5b56-169">スクリプトを一時停止するカスタム ショートカット</span><span class="sxs-lookup"><span data-stu-id="b5b56-169">Custom shortcut for pausing a script</span></span>  
:::image-end:::  

## <a name="introducing-the-microsoft-edge-tools-for-visual-studio-code-extension"></a><span data-ttu-id="b5b56-170">Microsoft Edge Tools for the microsoft Edge Tools for Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="b5b56-170">Introducing the Microsoft Edge Tools for Visual Studio Code extension</span></span>  

<span data-ttu-id="b5b56-171">コード**拡張機能Visual Studioネットワーク**Visual Studioの要素は\*\*\*\*、新しい Microsoft Edge Developer Tools for Visual Studio[コード拡張機能に統合][VisualStudioCodeMarketplaceMsEdgedevtools]されました。</span><span class="sxs-lookup"><span data-stu-id="b5b56-171">The **Elements for Visual Studio Code** and **Network for Visual Studio Code** extensions are now merged into the new [Microsoft Edge Developer Tools for Visual Studio Code][VisualStudioCodeMarketplaceMsEdgedevtools] extension.</span></span>  <span data-ttu-id="b5b56-172">Microsoft Edge DevTools を使用して、Microsoft のコードを離れることなく、次のVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="b5b56-172">Use the Microsoft Edge DevTools for the following activities without leaving Microsoft Visual Studio Code.</span></span>  

*   <span data-ttu-id="b5b56-173">DOM のデバッグ</span><span class="sxs-lookup"><span data-stu-id="b5b56-173">Debug the DOM</span></span>  
*   <span data-ttu-id="b5b56-174">CSS の編集</span><span class="sxs-lookup"><span data-stu-id="b5b56-174">Edit CSS</span></span>  
*   <span data-ttu-id="b5b56-175">ネットワーク トラフィックの検査</span><span class="sxs-lookup"><span data-stu-id="b5b56-175">Inspect network traffic</span></span>  

<span data-ttu-id="b5b56-176">拡張機能を使用して、Microsoft Edge を起動するか、ブラウザーの既存のインスタンスに接続するか、エディターから直接ヘッドレス ブラウザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-176">With the extension, launch Microsoft Edge, connect to an existing instance of the browser, or use a headless browser directly from your editor.</span></span>  <span data-ttu-id="b5b56-177">この拡張機能に関するフィードバックに関する問題の寄稿と提出を開始するには [、GitHub][GithubMicrosoftVscodeEdgeDevtools] の Microsoft Edge Developer Tools for Visual Studioコード リポジトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-177">To start contributing and filing issues with your feedback about this extension, navigate to the [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] repo on GitHub.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="ブラウザー モードの完全なスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         <span data-ttu-id="b5b56-179">ブラウザー モードの完全なスクリーンショットで拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="b5b56-179">Using the extension in full browser mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="ヘッドレス モードのスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         <span data-ttu-id="b5b56-181">ヘッドレス モードのスクリーンショットで拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="b5b56-181">Using the extension in headless mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="b5b56-182">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="b5b56-182">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-webauthn-tool"></a><span data-ttu-id="b5b56-183">新しい WebAuthn ツール</span><span class="sxs-lookup"><span data-stu-id="b5b56-183">New WebAuthn tool</span></span>  

<span data-ttu-id="b5b56-184">以前のバージョンの Microsoft Edge では、ネイティブの WebAuthn デバッグのサポートは行ってきていました。</span><span class="sxs-lookup"><span data-stu-id="b5b56-184">In earlier versions of Microsoft Edge, there was no native WebAuthn debugging support.</span></span>  <span data-ttu-id="b5b56-185">Web 認証 API を使用して Web アプリケーションをテストするには、物理認証 [機能が必要でした][GithubW3cWebauthn]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-185">You needed physical authenticators to test your web application with the [Web Authentication API][GithubW3cWebauthn].</span></span>  <span data-ttu-id="b5b56-186">新しい **WebAuthn ツールを使用** すると、物理認証機能を使用せずに次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-186">With the new **WebAuthn** tool, you are able to do the following actions without the use of any physical authenticators.</span></span>

*   <span data-ttu-id="b5b56-187">認証機能のエミュレート</span><span class="sxs-lookup"><span data-stu-id="b5b56-187">Emulate authenticators</span></span>
*   <span data-ttu-id="b5b56-188">オーセンティケーターの属性をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b5b56-188">Customize attributes of authenticators</span></span>
*   <span data-ttu-id="b5b56-189">オーセンティケータの状態を検査する</span><span class="sxs-lookup"><span data-stu-id="b5b56-189">Inspect states of authenticators</span></span>
    
<span data-ttu-id="b5b56-190">**WebAuthn 機能の詳細については、「Authenticators**のエミュレート」に移動し[、Microsoft Edge DevTools で WebAuthn をデバッグします][DevtoolsWebauthnIndex]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-190">For more information about the **WebAuthn** feature, navigate to [Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools][DevtoolsWebauthnIndex].</span></span>  

<span data-ttu-id="b5b56-191">新しい[WebAuthn][DevtoolsWebauthnIndex]ツールを使用して、オーセンティケーターをエミュレートし[、Web 認証 API][GithubW3cWebauthn]をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-191">You are able to emulate authenticators and debug the [Web Authentication API][GithubW3cWebauthn] with the new [WebAuthn][DevtoolsWebauthnIndex] tool.</span></span>  <span data-ttu-id="b5b56-192">**WebAuthn ツールを開く**場合は **、[DevTools** \( \) のカスタマイズと制御] アイコンを選択し、[ `...` その他> \*\*\*\*  >  **WebAuthn] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5b56-192">To open the **WebAuthn** tool, choose **the Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  <span data-ttu-id="b5b56-193">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイム更新プログラムを確認するには、[問題の修正] に[#1034663。][CR1034663]</span><span class="sxs-lookup"><span data-stu-id="b5b56-193">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1034663][CR1034663].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="WebAuthn ツールを開く" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         <span data-ttu-id="b5b56-195">**WebAuthn ツールを開**く</span><span class="sxs-lookup"><span data-stu-id="b5b56-195">Open the **WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn ツール" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         <span data-ttu-id="b5b56-197">**WebAuthn** ツール</span><span class="sxs-lookup"><span data-stu-id="b5b56-197">**WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="elements-tool-updates"></a><span data-ttu-id="b5b56-198">要素ツールの更新</span><span class="sxs-lookup"><span data-stu-id="b5b56-198">Elements tool updates</span></span>  

#### <a name="view-the-computed-sidebar-pane-in-the-styles-pane"></a><span data-ttu-id="b5b56-199">[スタイル] ウィンドウで [計算されたサイドバー] ウィンドウを表示する</span><span class="sxs-lookup"><span data-stu-id="b5b56-199">View the Computed sidebar pane in the Styles pane</span></span>  

<span data-ttu-id="b5b56-200">[スタイル **] ウィンドウの [** 計算] ウィンドウ **を切り替** えます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-200">Toggle the **Computed** pane in the **Styles** pane.</span></span>  <span data-ttu-id="b5b56-201">既定 **では、[スタイル]** ウィンドウ **の [計算** ] ウィンドウが折りたたまれています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-201">The **Computed** pane in the **Styles** pane is collapsed by default.</span></span>  <span data-ttu-id="b5b56-202">切り替えるには、ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-202">To toggle it, choose the button.</span></span>  <span data-ttu-id="b5b56-203">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[問題の修正] に[#1073899。][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="b5b56-203">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1073899][CR1073899].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="[計算] サイドバー ウィンドウを開く" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         <span data-ttu-id="b5b56-205">[計算 **] サイドバー ウィンドウを開** く</span><span class="sxs-lookup"><span data-stu-id="b5b56-205">Open the **Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="計算されたサイドバー ウィンドウ" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         <span data-ttu-id="b5b56-207">**計算されたサイドバー** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b5b56-207">**Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="grouping-css-properties-in-the-computed-panel"></a><span data-ttu-id="b5b56-208">[計算] パネルでの CSS プロパティのグループ化</span><span class="sxs-lookup"><span data-stu-id="b5b56-208">Grouping CSS properties in the Computed panel</span></span>  

<span data-ttu-id="b5b56-209">スクロールが少ない適用された CSS を表示するには、[計算] ウィンドウで CSS プロパティをカテゴリ別 **にグループ化** します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-209">To view your applied CSS with less scrolling, group the CSS properties by categories in the **Computed** pane.</span></span>  <span data-ttu-id="b5b56-210">CSS の検査中に、関連するプロパティのセットに選択的に集中することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-210">You may also selectively focus on a set of related properties while you inspect your CSS.</span></span>  <span data-ttu-id="b5b56-211">[要素 **] ツール** で、要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-211">From the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="b5b56-212">CSS プロパティを \(または ungroup\) グループ化するには、[グループ] チェック ボックスを **オンにします** 。</span><span class="sxs-lookup"><span data-stu-id="b5b56-212">To group \(or ungroup\) the CSS properties, toggle the **Group** checkbox.</span></span>  <span data-ttu-id="b5b56-213">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには[、[Issues][CR1096230]#1096230]、[#1084673]、および [#1106251][][CR1084673][に移動します][CR1106251]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-213">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1096230][CR1096230], [#1084673][CR1084673], and [#1106251][CR1106251].</span></span>  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="CSS プロパティのグループ化" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   <span data-ttu-id="b5b56-215">CSS プロパティのグループ化</span><span class="sxs-lookup"><span data-stu-id="b5b56-215">Grouping CSS properties</span></span>  
:::image-end:::  

### <a name="lighthouse-64-in-the-lighthouse-tool"></a><span data-ttu-id="b5b56-216">ライトハウス ツールのライトハウス 6.4</span><span class="sxs-lookup"><span data-stu-id="b5b56-216">Lighthouse 6.4 in the Lighthouse tool</span></span>  

<span data-ttu-id="b5b56-217">ライト **ハウス ツール** は現在、ライトハウス 6.4 を実行しています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-217">The **Lighthouse** tool is now running Lighthouse 6.4.</span></span>  <span data-ttu-id="b5b56-218">変更の完全な一覧については、ライトハウスの [リリース ノートに移動します][GithubGoogleChromeLighthouseReleasesV641]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-218">For a full list of changes, navigate to the [Lighthouse release notes][GithubGoogleChromeLighthouseReleasesV641].</span></span>  <span data-ttu-id="b5b56-219">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[問題の修正] に[#772558。][CR772558]</span><span class="sxs-lookup"><span data-stu-id="b5b56-219">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#772558][CR772558].</span></span>  

### <a name="performancemark-events-in-the-timings-section"></a><span data-ttu-id="b5b56-220">[タイミング] セクションの performance.mark() イベント</span><span class="sxs-lookup"><span data-stu-id="b5b56-220">performance.mark() events in the Timings section</span></span>  

<span data-ttu-id="b5b56-221">パフォーマンス **ツールの記録の** [タイミング] [セクションにイベント][DevtoolsGuideChromiumEvaluatePerformanceReference] がマーク `performance.mark()` されます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-221">The **Timings section** of a recording in the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool now marks `performance.mark()` events.</span></span>  <span data-ttu-id="b5b56-222">この機能を試して JavaScript コードのパフォーマンスを測定するには、コード `performance.mark()` にイベントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-222">To try this feature and measure the performance of your JavaScript code, add `performance.mark()` events to your code.</span></span>  <span data-ttu-id="b5b56-223">たとえば、次のコード スニペットは、ループの前と後にマーカーを追加し、7 の増分を使用して 0 から `for` 1000 まで反復します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-223">For example, the following code snippet adds markers before and after a `for` loop that iterates from 0 to 1000 using increments of 7.</span></span>  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

<span data-ttu-id="b5b56-224">次に、パフォーマンス ツール [を開][DevtoolsGuideChromiumEvaluatePerformanceReference] き、[タイミング] セクション **に移動して** JavaScript コードを記録します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-224">Then, open the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool and navigate to the **Timings section** to record your JavaScript code.</span></span>  <span data-ttu-id="b5b56-225">追加 `performance.mark()` したイベントが記録に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-225">The `performance.mark()` events you added are now displayed in the recording.</span></span>  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="Performance.mark イベント" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` <span data-ttu-id="b5b56-227">イベント</span><span class="sxs-lookup"><span data-stu-id="b5b56-227">events</span></span>  
:::image-end:::  

### <a name="new-resource-type-and-url-filters-in-the-network-tool"></a><span data-ttu-id="b5b56-228">ネットワーク ツールの新しいリソースの種類と URL フィルター</span><span class="sxs-lookup"><span data-stu-id="b5b56-228">New resource-type and url filters in the Network tool</span></span>  

<span data-ttu-id="b5b56-229">ネットワーク 要求を `resource-type` フィルター処理 `url` するには、 **ネットワーク** ツールの new キーワードとキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-229">Use the new `resource-type` and `url` keywords in the **Network** tool to filter network requests.</span></span>  <span data-ttu-id="b5b56-230">たとえば、画像 `resource-type:image` であるネットワーク要求に焦点を当てる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-230">For example, use `resource-type:image` to focus on the network requests that are images.</span></span>  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="リソース型フィルター" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   <span data-ttu-id="b5b56-232">リソース型フィルター</span><span class="sxs-lookup"><span data-stu-id="b5b56-232">resource-type filter</span></span>  
:::image-end:::  

<span data-ttu-id="b5b56-233">などの特別なキーワードを検索するには、 `resource-type` `url` プロパティで要求 [をフィルター処理します][DevtoolsNetworkReferenceFilterRequestsProperties]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-233">To discover more special keywords such as `resource-type` and `url`, navigate to [filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties].</span></span>  <span data-ttu-id="b5b56-234">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[[][CR1121141]問題] と [#1121141] に[#1104188。][CR1104188]</span><span class="sxs-lookup"><span data-stu-id="b5b56-234">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1121141][CR1121141] and [#1104188][CR1104188].</span></span>  

### <a name="frame-details-view-updates"></a><span data-ttu-id="b5b56-235">フレーム詳細ビューの更新</span><span class="sxs-lookup"><span data-stu-id="b5b56-235">Frame details view updates</span></span>  

#### <a name="display-coep-and-coop-reporting-to-endpoint"></a><span data-ttu-id="b5b56-236">COEP レポートと COOP レポートをエンドポイントに表示する</span><span class="sxs-lookup"><span data-stu-id="b5b56-236">Display COEP and COOP reporting to endpoint</span></span>  

<span data-ttu-id="b5b56-237">[セキュリティと分離] セクションの下で、クロスオリジン エンベダー ポリシー \(COEP\) およびクロスオリジン Opener Policy \(COOP\) `reporting to` **エンドポイント&表示** します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-237">View the Cross-Origin Embedder Policy \(COEP\) and Cross-Origin Opener Policy \(COOP\) `reporting to` endpoint under the **Security & Isolation** section.</span></span>  <span data-ttu-id="b5b56-238">Reporting [API では、][MdnReportingApi] 新しい HTTP ヘッダーが定義され、警告とエラーを送信するブラウザーのサーバー エンドポイント `Report-To` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-238">The [Reporting API][MdnReportingApi] defines `Report-To`, a new HTTP header, that gives you a way to specify the server endpoints for the browser to send warnings and errors.</span></span>  <span data-ttu-id="b5b56-239">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[問題の修正] に[#1051466。][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="b5b56-239">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="エンドポイントへのレポート" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   <span data-ttu-id="b5b56-241">エンドポイント `reporting to`</span><span class="sxs-lookup"><span data-stu-id="b5b56-241">The `reporting to` endpoint</span></span>  
:::image-end:::  

#### <a name="display-coep-and-coop-report-only-mode"></a><span data-ttu-id="b5b56-242">COEP および COOP レポート専用モードの表示</span><span class="sxs-lookup"><span data-stu-id="b5b56-242">Display COEP and COOP report-only mode</span></span>  

<span data-ttu-id="b5b56-243">DevTools では、 `report-only` モードに設定されている COEP と COOP のラベルが表示 `report-only` されます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-243">DevTools now display the `report-only` label for COEP and COOP that are set to `report-only` mode.</span></span>  <span data-ttu-id="b5b56-244">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[問題の修正] に[#1051466。][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="b5b56-244">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="レポート専用モード ラベル" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   <span data-ttu-id="b5b56-246">モード `report-only` ラベル</span><span class="sxs-lookup"><span data-stu-id="b5b56-246">The `report-only` mode label</span></span>  
:::image-end:::  

### <a name="view-and-fix-color-contrast-issues-in-the-css-overview-tool"></a><span data-ttu-id="b5b56-247">CSS の概要ツールで色のコントラストの問題を表示および修正する</span><span class="sxs-lookup"><span data-stu-id="b5b56-247">View and fix color contrast issues in the CSS Overview tool</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   <span data-ttu-id="b5b56-249">試験的機能</span><span class="sxs-lookup"><span data-stu-id="b5b56-249">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="b5b56-250">**CSS の概要ツール**で、色のコントラストに問題がある要素の一覧がページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-250">The **CSS Overview** tool now displays a list of elements on your page that have color contrast issues.</span></span>  <span data-ttu-id="b5b56-251">次のデモ ページには、色のコントラストの問題の例があります。</span><span class="sxs-lookup"><span data-stu-id="b5b56-251">The following demo page has an example of a color contrast issue.</span></span>  

[<span data-ttu-id="b5b56-252">CSS の概要 アクセス可能な色のデモ</span><span class="sxs-lookup"><span data-stu-id="b5b56-252">CSS Overview Accessible Colors Demo</span></span>][GlitchCssOverviewAccessibleColorsDemo]  

<span data-ttu-id="b5b56-253">この実験を有効にするには、[設定の実験 **]**  >  **で、[CSS**の概要] チェック**ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="b5b56-253">To enable this experiment, under **Settings** > **Experiments**, choose the **CSS Overview** checkbox.</span></span>  <span data-ttu-id="b5b56-254">色のコントラストに問題がある要素の一覧を表示するには、[ **コントラスト**] の問題で、[テキスト] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5b56-254">To view a list of elements that have a color contrast issue, on **Contrast issues**, choose **Text**.</span></span>  <span data-ttu-id="b5b56-255">要素ツールで要素を **開く** 場合は、一覧で要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5b56-255">To open the element in the **Elements** tool, choose an element in the list.</span></span>  <span data-ttu-id="b5b56-256">コントラストの問題を解決するために、Microsoft Edge DevTools は自動的 [に色の提案を提供します][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。</span><span class="sxs-lookup"><span data-stu-id="b5b56-256">To help fix contrast issues, the Microsoft Edge DevTools [automatically provide color suggestions][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane].</span></span>  <span data-ttu-id="b5b56-257">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、[ファイルの発行] に[#1120316。][CR1120316]</span><span class="sxs-lookup"><span data-stu-id="b5b56-257">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1120316][CR1120316].</span></span>  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低色コントラストの問題" lightbox="../../media/2020/10/css-overview.msft.png":::
   <span data-ttu-id="b5b56-259">低色コントラストの問題</span><span class="sxs-lookup"><span data-stu-id="b5b56-259">Low color contrast issues</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="b5b56-260">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="b5b56-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="b5b56-261">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b5b56-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="b5b56-262">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b5b56-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="b5b56-263">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="b5b56-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "要素ツールの [プロパティ] ウィンドウの廃止 - DevTools (Microsoft Edge 84) の新機能|Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS グリッドのデバッグ機能 - 新機能 DevTools (Microsoft Edge 85) |Microsoft Docs"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane "[スタイル] ウィンドウの [アクセス可能な色の提案] - DevTools の新機能 (Microsoft Edge 86) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "パフォーマンス分析|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "試験的な API を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボード ショートカット エディターを有効にする - 実験的な|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "ネットワーク コンソールを有効にする - 実験的な|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース オーダー ビューアーを有効にする - 試験的機能 | Microsoft Docs"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式デバイスとデュアルスクリーン デバイスのテスト - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験機能を有効にする - 実験的な|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "table - コンソール API リファレンス | Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける | Microsoft Docs"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "CSS グリッド の検査|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでレンダリング パフォーマンスを分析する - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "メディア プレーヤーの情報を表示およびデバッグ|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "プロパティ別に要求をフィルター処理する - ネットワーク分析の参照|Microsoft Docs"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "Microsoft Edge DevTools サーバーでオーセンティケーターをエミュレートし、WebAuthn をデバッグ|Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード |Visual Studioコード"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium bugs"
[CR772558]: https://crbug.com/772558 "DevTools: Lighthouse の最新バージョンに更新する | Chromium bugs"  
[CR1034663]: https://crbug.com/1034663 "WebAuthn テスト API のフロントエンドを作成|クロムのバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/Table ツーリング | Chromium bugs"  
[CR1051466]: https://crbug.com/1051466 "DevTools での COOP/COEP デバッグのサポート | Chromium bugs"  
[CR1073899]: https://crbug.com/1073899 "計算済みのスタイル タブが応答モードで表示されない | Chromium のバグ"  
[CR1075732]: https://crbug.com/1075732 "DevTools 個人用設定 - 移動可能なタブ |クロムのバグ"  
[CR1084673]: https://crbug.com/1084673 "DevTools: CSS カスタム プロパティの表示方法を改善します (別名)。CSS 変数) とその値|クロムのバグ"  
[CR1093687]: https://crbug.com/1093687 "統合ネットワーク要求を作成および再生するためのツールを作成する | Chromium のバグ"  
[CR1096230]: https://crbug.com/1096230 "[計算スタイル] ウィンドウの [カテゴリ別に CSS プロパティをグループ化|クロムのバグ"  
[CR1104188]: https://crbug.com/1104188 "完全な URL ファイルを検索しても、ネットワーク ツールの検索で結果が|クロムのバグ"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools: [計算スタイル] タブを改善|クロムのバグ"  
[CR1120316]: https://crbug.com/1120316 "[CSS の概要] の [色] の下で>コントラストを|クロム バグ"  
[CR1121141]: https://crbug.com/1121141 "ネットワーク ログ のリソースの種類によるフィルター処理を許可|クロムのバグ"  
[CR1121312]: https://crbug.com/1121312 "設定は、[その他のツール] メニュー ページから削除|クロムのバグ"  
[CR1136394]: https://crbug.com/1136394 "Flexbox ツール |クロム バグ"  
[CR1136655]: https://crbug.com/1136655 "Devtools: ローカライズ V2 |クロムのバグ"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "レポート API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v6.4.1 - GoogleChrome/ライトハウス |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証|GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "Hello! |Glitch"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman コレクション形式 v2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 仕様|スワッガー"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> <span data-ttu-id="b5b56-316">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-316">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b5b56-317">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/10/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="b5b56-317">The original page is found [here](https://developers.google.com/web/updates/2020/10/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b5b56-319">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b5b56-319">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
