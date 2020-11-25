---
description: 新しい CSS Grid のデバッグツール、Webauthn ツール、移動可能ツール、および計算されたサイドバーパネル。
title: DevTools の新機能 (Microsoft Edge 87)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b972468ad21f3a64985a00aecbe29836032b3334
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "11190006"
---
# <span data-ttu-id="4231e-104">DevTools の新機能 (Microsoft Edge 87)</span><span class="sxs-lookup"><span data-stu-id="4231e-104">What's New In DevTools (Microsoft Edge 87)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <span data-ttu-id="4231e-105">DevTools のローカライズの改善</span><span class="sxs-lookup"><span data-stu-id="4231e-105">Improving DevTools localization</span></span>  

<span data-ttu-id="4231e-106">翻訳のニーズを満たすために、Microsoft Edge DevTools チームは翻訳品質を向上させることに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="4231e-106">To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.</span></span>  <span data-ttu-id="4231e-107">Microsoft Edge バージョン87以降では、いくつかの文字列と用語がロックされており、他の DevTools が他の言語で表示されている場合でも変更されません。</span><span class="sxs-lookup"><span data-stu-id="4231e-107">Starting in Microsoft Edge version 87, several strings and terms are locked and do not change even when the rest of the DevTools are displayed in other languages.</span></span>  <span data-ttu-id="4231e-108">影響を受ける文字列と用語の一覧には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="4231e-108">The list of affected strings and terms include the following.</span></span>  

*   <span data-ttu-id="4231e-109">**Lighthouse**ツールの文字列。</span><span class="sxs-lookup"><span data-stu-id="4231e-109">The strings in the **Lighthouse** tool.</span></span>  
*   <span data-ttu-id="4231e-110">用語 `service worker` 。</span><span class="sxs-lookup"><span data-stu-id="4231e-110">The term `service worker`.</span></span>  
*   <span data-ttu-id="4231e-111">**ネットワーク**ツールには、、、、などのフィルターがあり `URL` `XHR` `JS` `CSS` ます。</span><span class="sxs-lookup"><span data-stu-id="4231e-111">Some of the **Network** tool filters such as `URL`, `XHR`, `JS`, and `CSS`.</span></span>  
*   <span data-ttu-id="4231e-112">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]コンソールユーティリティ API。</span><span class="sxs-lookup"><span data-stu-id="4231e-112">The [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] Console Utilities API.</span></span>  
    
<span data-ttu-id="4231e-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] は、devtools のローカライズされたバージョンでのユーザーの [コンソール](/microsoft-edge/devtools-guide-chromium/console/index.md) で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4231e-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] is now available in the [Console](/microsoft-edge/devtools-guide-chromium/console/index.md) for users on localized versions of the DevTools.</span></span>   <span data-ttu-id="4231e-114">Microsoft Edge DevTools のローカライズの改善に向けて、世界中の開発者コミュニティに感謝します。</span><span class="sxs-lookup"><span data-stu-id="4231e-114">Thank you to the global developer community for helping improve localization of the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="4231e-115">すべてのロケールでの DevTools のサポートを向上させるために、引き続き [ローカリゼーションの品質に関するフィードバックを送信して](#getting-in-touch-with-microsoft-edge-devtools-team) ください。</span><span class="sxs-lookup"><span data-stu-id="4231e-115">Continue to [send feedback on localization quality](#getting-in-touch-with-microsoft-edge-devtools-team) to improve support for DevTools in all locales.</span></span>  <span data-ttu-id="4231e-116">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1136655][CR1136655]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-116">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   <span data-ttu-id="4231e-118">ローカライズされていないフィルターが表示された**ネットワーク**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="4231e-118">**Network** pane with non-localized filters</span></span>  
:::image-end:::  

## <span data-ttu-id="4231e-119">上下パネル間の移動ツール</span><span class="sxs-lookup"><span data-stu-id="4231e-119">Move tools between top and bottom panels</span></span>  

<span data-ttu-id="4231e-120">DevTools では、上と下のパネル間の移動ツールがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4231e-120">DevTools now supports moving tools between the top and bottom panels.</span></span>  <span data-ttu-id="4231e-121">同時に2つのツールを自由に組み合わせて表示して、開発者向けツールをカスタマイズして生産性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="4231e-121">Customize your DevTools and improve your productivity by viewing any combination of two tools at the same time.</span></span>  <span data-ttu-id="4231e-122">たとえば、 **要素** と **ソース** ツールを ( **ソース** ツールを下に移動することによって) 表示します。</span><span class="sxs-lookup"><span data-stu-id="4231e-122">For example, view the **Elements** and the **Sources** tools at the same time \(by moving the **Sources** tool to the bottom\).</span></span>  <span data-ttu-id="4231e-123">Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、[懸案事項の [#1075732][CR1075732]に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-123">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1075732][CR1075732].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="4231e-124">一番上のツールを下に移動するには、タブをポイントしてコンテキストメニューを開き (\ を右クリックし)、[ **下へ移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4231e-124">To move any top tool to the bottom, hover on a tab, open the contextual menu \(right-click\), and choose **Move to bottom**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="下へ移動" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         <span data-ttu-id="4231e-126">下へ移動</span><span class="sxs-lookup"><span data-stu-id="4231e-126">Move to bottom</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="4231e-127">一番下にあるツールを一番上に移動するには、タブ上にカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、[ **先頭へ移動**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4231e-127">To move any bottom tool to the top, hover on a tab, open the contextual menu \(right-click\), and choose **Move to top**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="先頭に移動" lightbox="../../media/2020/10/move-to-top.msft.png":::
         <span data-ttu-id="4231e-129">先頭に移動</span><span class="sxs-lookup"><span data-stu-id="4231e-129">Move to top</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## <span data-ttu-id="4231e-130">ネットワークコンソールを使用した保存とエクスポート</span><span class="sxs-lookup"><span data-stu-id="4231e-130">Save and export using the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="4231e-132">実験的機能</span><span class="sxs-lookup"><span data-stu-id="4231e-132">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="4231e-133">**ネットワークコンソール**ツールでは、 [Postman v 2.1][PostmanSchemaJsonCollectionv210Index]スキーマと[openapi v2][SwaggerSpecificationV2]スキーマとの互換性が改善されました。</span><span class="sxs-lookup"><span data-stu-id="4231e-133">The **Network Console** tool now has improved compatibility with the [Postman v2.1][PostmanSchemaJsonCollectionv210Index] and [OpenAPI v2][SwaggerSpecificationV2] schemas.</span></span>  <span data-ttu-id="4231e-134">実験を有効にするには、「 [実験的な機能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] を有効にする」に移動し、[ **ネットワーク本体を有効**にする] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4231e-134">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Network Console**.</span></span>  <span data-ttu-id="4231e-135">**ネットワークコンソール**の詳細については、「[ネットワーク本体の実験的機能を有効][DevtoolsExperimentalFeaturesEnableNetworkConsole]にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4231e-135">For more information about the **Network Console**, navigate to [Enable Network Console Experimental feature][DevtoolsExperimentalFeaturesEnableNetworkConsole].</span></span>  <span data-ttu-id="4231e-136">この実験では、次の操作がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4231e-136">This experiment now supports the following actions.</span></span>  

*   <span data-ttu-id="4231e-137">コレクションと環境を保存し、エクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4231e-137">Save and export Collections and Environments.</span></span>  
*   <span data-ttu-id="4231e-138">**ネットワークコンソール**ツール内の環境変数のセットを編集およびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4231e-138">Edit and export sets of environment variables within the **Network Console** tool.</span></span>  
    
<span data-ttu-id="4231e-139">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1093687][CR1093687]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-139">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1093687][CR1093687].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="新しい環境の名前を入力する" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         <span data-ttu-id="4231e-141">新しい環境の名前を入力する</span><span class="sxs-lookup"><span data-stu-id="4231e-141">Enter name for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="新しい環境の形式を選ぶ" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         <span data-ttu-id="4231e-143">新しい環境の形式を選ぶ</span><span class="sxs-lookup"><span data-stu-id="4231e-143">Choose format for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="4231e-144">強化された CSS Grid ツール</span><span class="sxs-lookup"><span data-stu-id="4231e-144">Improved CSS Grid tooling</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="4231e-146">実験的機能</span><span class="sxs-lookup"><span data-stu-id="4231e-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="4231e-147">Microsoft Edge DevTools では、CSS グリッドの検査、表示、デバッグのための次の機能がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4231e-147">The Microsoft Edge DevTools now support the following features for inspecting, viewing, and debugging your CSS grids.</span></span>  

*   <span data-ttu-id="4231e-148">**検査**ツールを使用してシンプルなグリッドオーバーレイを表示するか、持続的なオーバーレイを使って詳細な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4231e-148">Display a simplified grid overlay using the **Inspect** tool, or get more detailed information with persistent overlays.</span></span>  
*   <span data-ttu-id="4231e-149">永続的なグリッドオーバーレイを有効にするには、 **要素** ツールで grid コンテナー要素の横にあるグリッドアイコンを選択するか、 **レイアウト** ツールでグリッドを選択します。</span><span class="sxs-lookup"><span data-stu-id="4231e-149">To enable persistent grid overlays, choose the grid icon next to a grid container element in the **Elements** tool or choose the grid in the **Layout** tool.</span></span>  
*   <span data-ttu-id="4231e-150">複数のグリッドに対して持続的なオーバーレイを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4231e-150">You may enable persistent overlays for multiple grids.</span></span>  
*   <span data-ttu-id="4231e-151">新しい **レイアウト** ツールでは、グリッドのオーバーレイを簡単に切り替えて、それぞれの外観と内容を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4231e-151">The new **Layout** tool allows you to easily toggle grid overlays and configure the appearance and the content for each.</span></span>  
    
<span data-ttu-id="4231e-152">これらの機能は、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4231e-152">The features are turned on by default.</span></span>  <span data-ttu-id="4231e-153">機能の詳細については、「 [CSS グリッド][DevtoolsCssGrid]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4231e-153">For more information about the features, navigate to [CSS grids][DevtoolsCssGrid].</span></span>  <span data-ttu-id="4231e-154">Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、[懸案事項の [#1047356][CR1047356]に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-154">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1047356][CR1047356].</span></span>  <span data-ttu-id="4231e-155">さらに、Microsoft Edge DevTools チームでは、Chromium コミュニティを使用して、新しい flexbox ツール機能を DevTools に追加しています。</span><span class="sxs-lookup"><span data-stu-id="4231e-155">Additionally, the Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new flexbox tooling features to DevTools.</span></span>  <span data-ttu-id="4231e-156">Chromium のオープンソースプロジェクトの flexbox ツーリングでの更新については、[問題の [#1136394][CR1136394]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-156">For updates on flexbox tooling in the Chromium open-source project, navigate to Issue [#1136394][CR1136394].</span></span>  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="グリッド付きレイアウトツール" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   <span data-ttu-id="4231e-158">グリッド付き**レイアウト**ツール</span><span class="sxs-lookup"><span data-stu-id="4231e-158">**Layout** tool with grids</span></span>  
:::image-end:::  

## <span data-ttu-id="4231e-159">設定のショートカットキーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="4231e-159">Customize keyboard shortcuts in Settings</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="4231e-161">実験的機能</span><span class="sxs-lookup"><span data-stu-id="4231e-161">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="4231e-162">DevTools で操作のキーボードショートカットをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4231e-162">You are now able to customize the keyboard shortcut for any action in the DevTools.</span></span>  <span data-ttu-id="4231e-163">Microsoft Edge バージョン84以降では、[キーボードショートカット][DevtoolsCustomizeShortcuts]の**Visual Studio コード**と**devtools (既定)** プリセットのいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="4231e-163">Since Microsoft Edge version 84, you are able to choose between **Visual Studio Code** and **DevTools (default)** presets for [keyboard shortcuts][DevtoolsCustomizeShortcuts].</span></span>  <span data-ttu-id="4231e-164">Microsoft Edge バージョン87以降では、キーボードショートカットの **有効化を有効** にすることで、 [キーボードショートカット][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]をさらにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="4231e-164">Starting in Microsoft Edge version 87, you may turn on the **Enable keyboard shortcut editor** experiment to further [customize keyboard shortcuts][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="4231e-165">実験を有効にするには、「 [実験的な機能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] を有効にする」に移動し、[ショートカットキーを **有効**にする] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4231e-165">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="4231e-166">ショートカットのカスタマイズと編集について詳しくは、「 [キーボードショートカットエディターの実験的機能を有効][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4231e-166">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  <span data-ttu-id="4231e-167">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#174309][CR174309]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-167">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="スクリプトを一時停止するためのカスタムショートカット" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   <span data-ttu-id="4231e-169">スクリプトを一時停止するためのカスタムショートカット</span><span class="sxs-lookup"><span data-stu-id="4231e-169">Custom shortcut for pausing a script</span></span>  
:::image-end:::  

## <span data-ttu-id="4231e-170">Microsoft Edge Tools for Visual Studio のコード拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="4231e-170">Introducing the Microsoft Edge Tools for Visual Studio Code extension</span></span>  

<span data-ttu-id="4231e-171">Visual studio**コードおよび visual studio コード拡張**用の**要素**は、 [Microsoft Edge 開発者向けの visual studio コード拡張用][VisualStudioCodeMarketplaceMsEdgedevtools]の新しいツールにマージされました。</span><span class="sxs-lookup"><span data-stu-id="4231e-171">The **Elements for Visual Studio Code** and **Network for Visual Studio Code** extensions are now merged into the new [Microsoft Edge Developer Tools for Visual Studio Code][VisualStudioCodeMarketplaceMsEdgedevtools] extension.</span></span>  <span data-ttu-id="4231e-172">Visual Studio コードを終了せずに、次のアクティビティには Microsoft Edge DevTools を使用します。</span><span class="sxs-lookup"><span data-stu-id="4231e-172">Use the Microsoft Edge DevTools for the following activities without leaving Visual Studio Code.</span></span>  

*   <span data-ttu-id="4231e-173">DOM をデバッグする</span><span class="sxs-lookup"><span data-stu-id="4231e-173">Debug the DOM</span></span>  
*   <span data-ttu-id="4231e-174">CSS を編集する</span><span class="sxs-lookup"><span data-stu-id="4231e-174">Edit CSS</span></span>  
*   <span data-ttu-id="4231e-175">ネットワークトラフィックを検査する</span><span class="sxs-lookup"><span data-stu-id="4231e-175">Inspect network traffic</span></span>  

<span data-ttu-id="4231e-176">拡張機能を使用して、Microsoft Edge を起動するか、ブラウザーの既存のインスタンスに接続するか、またはエディターから直接ヘッドレスブラウザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4231e-176">With the extension, launch Microsoft Edge, connect to an existing instance of the browser, or use a headless browser directly from your editor.</span></span>  <span data-ttu-id="4231e-177">この拡張機能についてのフィードバックを投稿して、問題の投稿とファイリングを開始するには、GitHub の [Visual Studio コードリポジトリ用 Microsoft Edge 開発者ツール][GithubMicrosoftVscodeEdgeDevtools] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-177">To start contributing and filing issues with your feedback about this extension, navigate to the [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] repo on GitHub.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="完全ブラウザーモードのスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         <span data-ttu-id="4231e-179">完全ブラウザーモードのスクリーンショットで拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="4231e-179">Using the extension in full browser mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="ヘッドレスモードのスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         <span data-ttu-id="4231e-181">ヘッドレスモードのスクリーンショットで拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="4231e-181">Using the extension in headless mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="4231e-182">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="4231e-182">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="4231e-183">新しい WebAuthn ツール</span><span class="sxs-lookup"><span data-stu-id="4231e-183">New WebAuthn tool</span></span>  

<span data-ttu-id="4231e-184">以前のバージョンの Microsoft Edge では、ネイティブの WebAuthn デバッグのサポートはありませんでした。</span><span class="sxs-lookup"><span data-stu-id="4231e-184">In earlier versions of Microsoft Edge, there was no native WebAuthn debugging support.</span></span>  <span data-ttu-id="4231e-185">Web アプリケーションを [Web 認証 API][GithubW3cWebauthn]でテストするには、物理認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="4231e-185">You needed physical authenticators to test your web application with the [Web Authentication API][GithubW3cWebauthn].</span></span>  <span data-ttu-id="4231e-186">新しい **WebAuthn** ツールを使用すると、物理的なオーセンティケータを使用せずに、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4231e-186">With the new **WebAuthn** tool, you are able to do the following actions without the use of any physical authenticators.</span></span>

*   <span data-ttu-id="4231e-187">オーセンティケータのエミュレート</span><span class="sxs-lookup"><span data-stu-id="4231e-187">Emulate authenticators</span></span>
*   <span data-ttu-id="4231e-188">オーセンティケータの属性をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="4231e-188">Customize attributes of authenticators</span></span>
*   <span data-ttu-id="4231e-189">オーセンティケータの状態を検査する</span><span class="sxs-lookup"><span data-stu-id="4231e-189">Inspect states of authenticators</span></span>
    
<span data-ttu-id="4231e-190">**WebAuthn**機能の詳細については、「 [Microsoft Edge devtools でオーセンティケータをエミュレートし、WebAuthn をデバッグする」][DevtoolsWebauthnIndex]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4231e-190">For more information about the **WebAuthn** feature, navigate to [Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools][DevtoolsWebauthnIndex].</span></span>  

<span data-ttu-id="4231e-191">新しい[WebAuthn][DevtoolsWebauthnIndex]ツールを使って、オーセンティケータをエミュレートし、 [Web 認証 API][GithubW3cWebauthn]をデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="4231e-191">You are able to emulate authenticators and debug the [Web Authentication API][GithubW3cWebauthn] with the new [WebAuthn][DevtoolsWebauthnIndex] tool.</span></span>  <span data-ttu-id="4231e-192">**Webauthn**ツールを開くには、[**ユーザー設定と制御のための devtools** \ ( `...` \)] アイコン > [**その他のツール**] WebAuthn を選び  >  **WebAuthn**ます。</span><span class="sxs-lookup"><span data-stu-id="4231e-192">To open the **WebAuthn** tool, choose **the Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  <span data-ttu-id="4231e-193">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1034663][CR1034663]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-193">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1034663][CR1034663].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="[WebAuthn] ツールを開く" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         <span data-ttu-id="4231e-195">[ **WebAuthn** ] ツールを開く</span><span class="sxs-lookup"><span data-stu-id="4231e-195">Open the **WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn ツール" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         <span data-ttu-id="4231e-197">**WebAuthn** ツール</span><span class="sxs-lookup"><span data-stu-id="4231e-197">**WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="4231e-198">要素ツールの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="4231e-198">Elements tool updates</span></span>  

#### <span data-ttu-id="4231e-199">[スタイル] ウィンドウの [計算されたサイドバー] ウィンドウを表示する</span><span class="sxs-lookup"><span data-stu-id="4231e-199">View the Computed sidebar pane in the Styles pane</span></span>  

<span data-ttu-id="4231e-200">[**スタイル**] ウィンドウで**計算**されたウィンドウを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4231e-200">Toggle the **Computed** pane in the **Styles** pane.</span></span>  <span data-ttu-id="4231e-201">既定では、[**スタイル**] ウィンドウの**計算**ウィンドウは折りたたまれています。</span><span class="sxs-lookup"><span data-stu-id="4231e-201">The **Computed** pane in the **Styles** pane is collapsed by default.</span></span>  <span data-ttu-id="4231e-202">切り替えを行うには、ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4231e-202">To toggle it, choose the button.</span></span>  <span data-ttu-id="4231e-203">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1073899][CR1073899]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-203">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1073899][CR1073899].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="[計算されたサイドバー] ウィンドウを開く" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         <span data-ttu-id="4231e-205">[計算された **サイドバー** ] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="4231e-205">Open the **Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="計算されたサイドバーウィンドウ" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         <span data-ttu-id="4231e-207">**計算** されたサイドバーウィンドウ</span><span class="sxs-lookup"><span data-stu-id="4231e-207">**Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="4231e-208">計算されたパネルでの CSS プロパティのグループ化</span><span class="sxs-lookup"><span data-stu-id="4231e-208">Grouping CSS properties in the Computed panel</span></span>  

<span data-ttu-id="4231e-209">適用した CSS のスクロールを減らして、CSS のプロパティをカテゴリ別にグループ化するには、[ **計算** ] ウィンドウの [カテゴリ別] をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="4231e-209">To view your applied CSS with less scrolling, group the CSS properties by categories in the **Computed** pane.</span></span>  <span data-ttu-id="4231e-210">CSS を検査しながら、一連の関連するプロパティに対して選択的にフォーカスを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4231e-210">You may also selectively focus on a set of related properties while you inspect your CSS.</span></span>  <span data-ttu-id="4231e-211">**要素**ツールで要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="4231e-211">From the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="4231e-212">[CSS のプロパティ] をグループ化またはグループ解除するには、[ **グループ化** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4231e-212">To group \(or ungroup\) the CSS properties, toggle the **Group** checkbox.</span></span>  <span data-ttu-id="4231e-213">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[ [#1096230][CR1096230]]、[ [#1084673][CR1084673]]、[ [#1106251][CR1106251]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-213">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1096230][CR1096230], [#1084673][CR1084673], and [#1106251][CR1106251].</span></span>  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="CSS プロパティのグループ化" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   <span data-ttu-id="4231e-215">CSS プロパティのグループ化</span><span class="sxs-lookup"><span data-stu-id="4231e-215">Grouping CSS properties</span></span>  
:::image-end:::  

### <span data-ttu-id="4231e-216">Lighthouse ツールの Lighthouse 6.4</span><span class="sxs-lookup"><span data-stu-id="4231e-216">Lighthouse 6.4 in the Lighthouse tool</span></span>  

<span data-ttu-id="4231e-217">**Lighthouse**ツールで Lighthouse 6.4 が実行されています。</span><span class="sxs-lookup"><span data-stu-id="4231e-217">The **Lighthouse** tool is now running Lighthouse 6.4.</span></span>  <span data-ttu-id="4231e-218">すべての変更の一覧については、 [Lighthouse のリリースノート][GithubGoogleChromeLighthouseReleasesV641]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4231e-218">For a full list of changes, navigate to the [Lighthouse release notes][GithubGoogleChromeLighthouseReleasesV641].</span></span>  <span data-ttu-id="4231e-219">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#772558][CR772558]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-219">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#772558][CR772558].</span></span>  

### <span data-ttu-id="4231e-220">[タイミング] セクションの performance. mark () イベント</span><span class="sxs-lookup"><span data-stu-id="4231e-220">performance.mark() events in the Timings section</span></span>  

<span data-ttu-id="4231e-221">[パフォーマンス][DevtoolsGuideChromiumEvaluatePerformanceReference]ツールの記録の [**タイミング] セクション**で、イベントがマークされるようになりました `performance.mark()` 。</span><span class="sxs-lookup"><span data-stu-id="4231e-221">The **Timings section** of a recording in the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool now marks `performance.mark()` events.</span></span>  <span data-ttu-id="4231e-222">この機能を試して、JavaScript コードのパフォーマンスを測定するには、 `performance.mark()` コードにイベントを追加します。</span><span class="sxs-lookup"><span data-stu-id="4231e-222">To try this feature and measure the performance of your JavaScript code, add `performance.mark()` events to your code.</span></span>  <span data-ttu-id="4231e-223">たとえば、次のコードスニペットでは、 `for` 7 のインクリメントを使用して0から1000までのループの前後にマーカーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4231e-223">For example, the following code snippet adds markers before and after a `for` loop that iterates from 0 to 1000 using increments of 7.</span></span>  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

<span data-ttu-id="4231e-224">次に、 [パフォーマンス][DevtoolsGuideChromiumEvaluatePerformanceReference] ツールを開き、[ **タイミング] セクション** に移動して、JavaScript コードを記録します。</span><span class="sxs-lookup"><span data-stu-id="4231e-224">Then, open the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool and navigate to the **Timings section** to record your JavaScript code.</span></span>  <span data-ttu-id="4231e-225">`performance.mark()`追加したイベントが記録に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4231e-225">The `performance.mark()` events you added are now displayed in the recording.</span></span>  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="パフォーマンス。イベントをマークする" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` <span data-ttu-id="4231e-227">事象</span><span class="sxs-lookup"><span data-stu-id="4231e-227">events</span></span>  
:::image-end:::  

### <span data-ttu-id="4231e-228">ネットワークツールの新しいリソースの種類と url のフィルター</span><span class="sxs-lookup"><span data-stu-id="4231e-228">New resource-type and url filters in the Network tool</span></span>  

<span data-ttu-id="4231e-229">ネットワークツールの新規とキーワードを使って、 `resource-type` `url` ネットワーク要求をフィルター処理します。 **Network**</span><span class="sxs-lookup"><span data-stu-id="4231e-229">Use the new `resource-type` and `url` keywords in the **Network** tool to filter network requests.</span></span>  <span data-ttu-id="4231e-230">たとえば、画像で `resource-type:image` あるネットワーク要求にフォーカスするために使用します。</span><span class="sxs-lookup"><span data-stu-id="4231e-230">For example, use `resource-type:image` to focus on the network requests that are images.</span></span>  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="リソースの種類フィルター" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   <span data-ttu-id="4231e-232">リソースの種類フィルター</span><span class="sxs-lookup"><span data-stu-id="4231e-232">resource-type filter</span></span>  
:::image-end:::  

<span data-ttu-id="4231e-233">などのその他の特殊なキーワードについて `resource-type` `url` は、「 [プロパティによる要求をフィルター処理][DevtoolsNetworkReferenceFilterRequestsProperties]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4231e-233">To discover more special keywords such as `resource-type` and `url`, navigate to [filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties].</span></span>  <span data-ttu-id="4231e-234">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [#1121141][CR1121141] と [#1104188][CR1104188]に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-234">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1121141][CR1121141] and [#1104188][CR1104188].</span></span>  

### <span data-ttu-id="4231e-235">フレームの詳細ビューの更新</span><span class="sxs-lookup"><span data-stu-id="4231e-235">Frame details view updates</span></span>  

#### <span data-ttu-id="4231e-236">COEP と CO-OP レポートをエンドポイントに表示</span><span class="sxs-lookup"><span data-stu-id="4231e-236">Display COEP and COOP reporting to endpoint</span></span>  

<span data-ttu-id="4231e-237">`reporting to`[**セキュリティ & 分離**] セクションで、cross-origin Embedder POLICY \ (coep \) と cross-origin Opener POLICY \ (co-op) エンドポイントを表示します。</span><span class="sxs-lookup"><span data-stu-id="4231e-237">View the Cross-Origin Embedder Policy \(COEP\) and Cross-Origin Opener Policy \(COOP\) `reporting to` endpoint under the **Security & Isolation** section.</span></span>  <span data-ttu-id="4231e-238">[レポート API][MdnReportingApi]では、新しい HTTP ヘッダーが定義され `Report-To` ています。これにより、ブラウザーのサーバーエンドポイントを指定して、警告やエラーを送信できます。</span><span class="sxs-lookup"><span data-stu-id="4231e-238">The [Reporting API][MdnReportingApi] defines `Report-To`, a new HTTP header, that gives you a way to specify the server endpoints for the browser to send warnings and errors.</span></span>  <span data-ttu-id="4231e-239">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1051466][CR1051466]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-239">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="レポート終了のエンドポイント" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   <span data-ttu-id="4231e-241">`reporting to`エンドポイント</span><span class="sxs-lookup"><span data-stu-id="4231e-241">The `reporting to` endpoint</span></span>  
:::image-end:::  

#### <span data-ttu-id="4231e-242">COEP および CO-OP レポート専用モードの表示</span><span class="sxs-lookup"><span data-stu-id="4231e-242">Display COEP and COOP report-only mode</span></span>  

<span data-ttu-id="4231e-243">`report-only`DEVTOOLS と co-op のラベルが表示されるようになりました。これは、モードに設定されてい `report-only` ます。</span><span class="sxs-lookup"><span data-stu-id="4231e-243">DevTools now display the `report-only` label for COEP and COOP that are set to `report-only` mode.</span></span>  <span data-ttu-id="4231e-244">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1051466][CR1051466]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-244">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="レポート専用モードのラベル" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   <span data-ttu-id="4231e-246">`report-only`モードラベル</span><span class="sxs-lookup"><span data-stu-id="4231e-246">The `report-only` mode label</span></span>  
:::image-end:::  

### <span data-ttu-id="4231e-247">CSS の概要ツールで色のコントラストの問題を表示して修正する</span><span class="sxs-lookup"><span data-stu-id="4231e-247">View and fix color contrast issues in the CSS Overview tool</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="4231e-249">実験的機能</span><span class="sxs-lookup"><span data-stu-id="4231e-249">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="4231e-250">**CSS の概要**ツールでは、色のコントラストの問題があるページの要素の一覧が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4231e-250">The **CSS Overview** tool now displays a list of elements on your page that have color contrast issues.</span></span>  <span data-ttu-id="4231e-251">次のデモページでは、色のコントラストの問題の例を示します。</span><span class="sxs-lookup"><span data-stu-id="4231e-251">The following demo page has an example of a color contrast issue.</span></span>  

[<span data-ttu-id="4231e-252">CSS の概要アクセシビリティの高い色のデモ</span><span class="sxs-lookup"><span data-stu-id="4231e-252">CSS Overview Accessible Colors Demo</span></span>][GlitchCssOverviewAccessibleColorsDemo]  

<span data-ttu-id="4231e-253">この実験を有効にするには、[**設定**の実験] で [  >  **Experiments** **CSS の概要**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4231e-253">To enable this experiment, under **Settings** > **Experiments**, choose the **CSS Overview** checkbox.</span></span>  <span data-ttu-id="4231e-254">色のコントラストの問題がある要素の一覧を表示するには、[ **コントラストの問題**] で [ **テキスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4231e-254">To view a list of elements that have a color contrast issue, on **Contrast issues**, choose **Text**.</span></span>  <span data-ttu-id="4231e-255">**要素ツールで**要素を開くには、リスト内の要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="4231e-255">To open the element in the **Elements** tool, choose an element in the list.</span></span>  <span data-ttu-id="4231e-256">コントラストの問題を解決するために、Microsoft Edge DevTools では [色候補が自動的に提供][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]されます。</span><span class="sxs-lookup"><span data-stu-id="4231e-256">To help fix contrast issues, the Microsoft Edge DevTools [automatically provide color suggestions][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane].</span></span>  <span data-ttu-id="4231e-257">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1120316][CR1120316]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4231e-257">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1120316][CR1120316].</span></span>  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低色のコントラストの問題" lightbox="../../media/2020/10/css-overview.msft.png":::
   <span data-ttu-id="4231e-259">低色のコントラストの問題</span><span class="sxs-lookup"><span data-stu-id="4231e-259">Low color contrast issues</span></span>  
:::image-end:::  

## <span data-ttu-id="4231e-260">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="4231e-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="4231e-261">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4231e-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="4231e-262">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4231e-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="4231e-263">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="4231e-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "要素ツールの [プロパティ] ウィンドウの廃止-DevTools の新機能 (Microsoft Edge 84) |Microsoft ドキュメント"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS grid のデバッグ機能-DevTools の新機能 (Microsoft Edge 85) |Microsoft ドキュメント"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane "[スタイル] ウィンドウでアクセシビリティの高い色の候補を表示する (DevTools の新機能 (Microsoft Edge 86) |Microsoft ドキュメント"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選んだ要素または JavaScript オブジェクト-コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "業績分析リファレンス |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "実験的な Api を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボードショートカットエディターを有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "ネットワーク本体の実験的機能を有効にする |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース注文ビューアーを有効にする-実験的な機能 |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式とデュアルスクリーンデバイスでのテスト-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験的な機能を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-コンソール API リファレンス |Microsoft ドキュメント"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブを使用して、使用されていない JavaScript と CSS コードを見つけます。Microsoft ドキュメント"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "CSS グリッドの検査 |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドローワ-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブの [パフォーマンス分析] 参照で、レンダリングのパフォーマンスを分析します。Microsoft ドキュメント"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "メディアプレーヤー情報を表示してデバッグする |Microsoft ドキュメント"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "プロパティによるフィルター要求-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "Microsoft Edge DevTools でオーセンティケータをエミュレートし、WebAuthn をデバッグします。Microsoft ドキュメント"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio コード"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード |Visual Studio コード"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボードショートカット/キーバインディングのカスタマイズを許可する |Chromium のバグ"
[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する |Chromium のバグ"  
[CR1034663]: https://crbug.com/1034663 "WebAuthn テスト API のフロントエンドを作成します。 |Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table ツーリング |Chromium のバグ"  
[CR1051466]: https://crbug.com/1051466 "DevTools での CO-OP/COEP のデバッグのサポート |Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "[計算されたスタイル] タブが応答モードで表示されなくなります。Chromium のバグ"  
[CR1075732]: https://crbug.com/1075732 "DevTools パーソナル化-移動可能なタブ |Chromium のバグ"  
[CR1084673]: https://crbug.com/1084673 "DevTools: CSS カスタムプロパティの表示方法を改善します ((別名)。CSS 変数) とその値 |Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "代理ネットワーク要求を作成および再生するためのツールを作成する |Chromium のバグ"  
[CR1096230]: https://crbug.com/1096230 "計算されたスタイルウィンドウのカテゴリ別のグループ CSS プロパティ |Chromium のバグ"  
[CR1104188]: https://crbug.com/1104188 "ネットワークツール検索で完全な URL を検索しても結果が見つかりません |Chromium のバグ"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools: [計算されたスタイルの改善] タブ |Chromium のバグ"  
[CR1120316]: https://crbug.com/1120316 "[CSS の概要 > 色] でコントラストの悪い箇所を強調表示する |Chromium のバグ"  
[CR1121141]: https://crbug.com/1121141 "ネットワークログでのリソースの種類によるフィルターの許可 |Chromium のバグ"  
[CR1121312]: https://crbug.com/1121312 "[その他のツール] メニューから設定を削除する必要があります。Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "Flexbox ツール |Chromium のバグ"  
[CR1136655]: https://crbug.com/1136655 "Devtools: ローカライズバージョン V2 |Chromium のバグ"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "レポート API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v 6.4.1-GoogleChrome/lighthouse |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証 |GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "こんにちは! |故障"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman コレクション形式 v 2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI の仕様 |Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> <span data-ttu-id="4231e-316">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4231e-316">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4231e-317">元のページは [ここ](https://developers.google.com/web/updates/2020/10/devtools/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。</span><span class="sxs-lookup"><span data-stu-id="4231e-317">The original page is found [here](https://developers.google.com/web/updates/2020/10/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4231e-319">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4231e-319">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  