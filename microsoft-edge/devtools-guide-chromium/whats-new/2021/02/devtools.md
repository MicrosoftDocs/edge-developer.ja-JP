---
description: CSS Flexbox のデバッグサポート、Web ページのパフォーマンス ヘッドアップ表示、ツールの更新プログラムの発行など
title: DevTools の新機能 (Microsoft Edge 90)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.localizationpriority: high
ms.openlocfilehash: e220bbbe0a545b7cc539d0c77deb2ecb070decc0
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439746"
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
# <a name="whats-new-in-devtools-microsoft-edge-90"></a><span data-ttu-id="38b77-104">DevTools の新機能 (Microsoft Edge 90)</span><span class="sxs-lookup"><span data-stu-id="38b77-104">What's New In DevTools (Microsoft Edge 90)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="group-tools-together-in-focus-mode"></a><span data-ttu-id="38b77-105">フォーカス モードでツールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="38b77-105">Group tools together in Focus Mode</span></span>  

<!-- Title: Grouping the tools in Focus Mode  -->  
<!-- Subtitle: Organize your favorite tools into groups with the new Focus Mode UI.  -->  

<span data-ttu-id="38b77-106">フォーカス モードは、独自のデバッグ シナリオに基づいてさまざまなツールをグループ化できる試験的なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="38b77-106">Focus Mode is an experimental interface that allows you to group different tools together based on your own debugging scenarios.</span></span>  <span data-ttu-id="38b77-107">左側に表示される新しい**アクティビティ バー**には、**レイアウト**や**デバッグ**などの定義済みのツール グループが含まれています。</span><span class="sxs-lookup"><span data-stu-id="38b77-107">The new **Activity Bar** displayed on the left includes predefined tool groups such as **Layout** and **Debugging**.</span></span>  <span data-ttu-id="38b77-108">各ツール グループをカスタマイズするには、**閉じる**\(`X`\) アイコンでツールを閉じるか、**[その他のツール]** \(`+`\) アイコンを使用して新しいツールを追加します。</span><span class="sxs-lookup"><span data-stu-id="38b77-108">To customize each tool group, close tools with the **Close** \(`X`\) icon or add new tools with the **More tools** \(`+`\) icon.</span></span>  

<span data-ttu-id="38b77-109">試験を有効にするには、[[試験的機能を有効にする]][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] に移動し、**[フォーカス モード] と[DevTools ツールヒント]** と **[有効にする] + [ボタン] タブ メニューの横にあるチェック ボックスをオンにして、その他のツールを開きます**。</span><span class="sxs-lookup"><span data-stu-id="38b77-109">To turn on the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] and choose the checkboxes next to **Focus Mode and DevTools Tooltips** and **Enable + button tab menus to open more tools**.</span></span>  <span data-ttu-id="38b77-110">この機能の詳細、または質問やアイデアをコメントするには、[DevTools: フォーカス モード UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-110">For more information about this feature or to comment with questions and ideas, navigate to [DevTools: Focus Mode UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer].</span></span>  

:::image type="complex" source="../../media/2021/02/focus-mode.msft.png" alt-text="アクティビティ バーを表示する" lightbox="../../media/2021/02/focus-mode.msft.png":::
   <span data-ttu-id="38b77-112">**アクティビティ バー** を表示する</span><span class="sxs-lookup"><span data-stu-id="38b77-112">Display the **Activity Bar**</span></span>  
:::image-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a><span data-ttu-id="38b77-113">有益なツール ヒントを使用した DevTools の詳細</span><span class="sxs-lookup"><span data-stu-id="38b77-113">Learn about DevTools with informative tooltips</span></span>  

<!-- Title: DevTools Tooltips  -->  
<!-- Subtitle: Learn more about how to use DevTools with informative DevTools tooltips.  -->  

<span data-ttu-id="38b77-114">DevTools ツール ヒント機能を使用すると、さまざまなツールとウィンドウについて学習できます。</span><span class="sxs-lookup"><span data-stu-id="38b77-114">The DevTools Tooltips feature helps you learn about all the different tools and panes.</span></span>  <span data-ttu-id="38b77-115">DevTools のツールヒントを切り替えるには、**アクティビティ バー**の下部にあるヘルプ \(`?`\)アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-115">Choose the Help \(`?`\) icon at the bottom of the **Activity Bar** to toggle tooltips in the DevTools.</span></span>  <span data-ttu-id="38b77-116">ツールヒントがオンの場合は、DevTools のアウトライン領域にマウス ポインターを合わせると、ツールの使い方の詳細が確認できます。</span><span class="sxs-lookup"><span data-stu-id="38b77-116">When tooltips are on, hover over each outlined region of DevTools to learn more about how to use the tool.</span></span>  <span data-ttu-id="38b77-117">試験を有効にするには、[[試験的機能を有効にする]][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] に移動し、**[フォーカス モード] と[DevTools ツールヒント]** と **[有効にする] + [ボタン] タブ メニューの横にあるチェック ボックスをオンにして、その他のツールを開きます**。</span><span class="sxs-lookup"><span data-stu-id="38b77-117">To turn on the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] and choose the checkboxes next to **Focus Mode and DevTools Tooltips** and **Enable + button tab menus to open more tools**.</span></span>  <span data-ttu-id="38b77-118">この機能の詳細、または質問やアイデアをコメントするには、[DevTools: フォーカス モード UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-118">For more information about this feature or to comment with questions and ideas, navigate to [DevTools: Focus Mode UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer].</span></span>  

:::image type="complex" source="../../media/2021/02/focus-mode-and-tooltips-help.msft.png" alt-text="アクティビティ バーの [ヘルプ ] (?) アイコンを選択して、ヒントを表示する" lightbox="../../media/2021/02/focus-mode-and-tooltips-help.msft.png":::
   <span data-ttu-id="38b77-120">ヒントを表示するには、**アクティビティ バー**の[ヘルプ \(`?`\) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-120">Choose the Help \(`?`\) icon in the **Activity Bar** to display tooltips</span></span>  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a><span data-ttu-id="38b77-121">[設定] でキーボード ショートカットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="38b77-121">Customize keyboard shortcuts in Settings</span></span>  

<!-- Title: Change keyboard shortcuts in Settings  -->  
<!-- TODO:  Rachel's feedback is about the fact that this experimental feature is turned on by default, may have separate section in What's New for experimental features)  -->  
<!-- Subtitle: Make DevTools work better for you by creating new keyboard shortcuts for any action in the DevTools.  -->  

<span data-ttu-id="38b77-122">これで、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="38b77-122">You may now customize the keyboard shortcut for any action in the DevTools.</span></span>  <span data-ttu-id="38b77-123">キーボード ショートカットを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="38b77-123">To edit a keyboard shortcut, complete the following actions.</span></span>  

1.  <span data-ttu-id="38b77-124">DevTools を開き、**[設定]** > \*\* [ショートカット]\*\* を選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-124">Open the DevTools, and then choose **Settings** > **Shortcuts**.</span></span>  
1.  <span data-ttu-id="38b77-125">カスタマイズするアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-125">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="38b77-126">[編集] \(</span><span class="sxs-lookup"><span data-stu-id="38b77-126">Choose the Edit \(</span></span>![[キーボード ショートカットの編集] アイコン](../../media/2021/02/edit-keyboard-shortcut-icon.msft.png)<span data-ttu-id="38b77-128">\) アイコン。</span><span class="sxs-lookup"><span data-stu-id="38b77-128">\) icon.</span></span>  
1.  <span data-ttu-id="38b77-129">アクションにバインドするキーを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-129">Select the keys you want to bind to the action.</span></span>  
1.  <span data-ttu-id="38b77-130">チェックマーク \( を選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-130">Choose the checkmark \(</span></span>![チェックマークのキーボード ショートカット アイコン](../../media/2021/02/checkmark-keyboard-shortcut-icon.msft.png)<span data-ttu-id="38b77-132">\) アイコン。</span><span class="sxs-lookup"><span data-stu-id="38b77-132">\) icon.</span></span>  
    
<span data-ttu-id="38b77-133">ショートカットのカスタマイズと編集の詳細については、「[Microsoft Edge DevToolsでキーボード ショートカットをカスタマイズする][DevtoolsCustomizeShortcuts]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-133">For more information about customizing and editing shortcuts, navigate to [Customize keyboard shortcuts in the Microsoft Edge DevTools][DevtoolsCustomizeShortcuts].</span></span>  <span data-ttu-id="38b77-134">Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、Issue [174309][CR174309] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-134">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png" alt-text="編集モードのショートカットを使用して、ショートカットの DevTools 設定でキーボード ショートカットをカスタマイズする" lightbox="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png":::
   <span data-ttu-id="38b77-136">編集モードのショートカットを使用して、ショートカットの [DevTools 設定][DevtoolsCustomizeIndexSettings] でキーボード ショートカットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="38b77-136">Customize keyboard shortcuts in the [DevTools Settings][DevtoolsCustomizeIndexSettings] on Shortcuts with a shortcut in edit mode</span></span>  
:::image-end:::  

## <a name="microsoft-edge-devtools-for-visual-studio-code-extension-update-114"></a><span data-ttu-id="38b77-137">Microsoft Edge DevTools for Visual Studio Code 拡張機能更新プログラム 1.1.4</span><span class="sxs-lookup"><span data-stu-id="38b77-137">Microsoft Edge DevTools for Visual Studio Code extension update 1.1.4</span></span>  

<!-- Title: Edge Devtools for Visual Studio code extension update 1.1.4  -->  
<!-- Subtitle: Latest changes including a favicon is displayed next to each of the instances and console messages from the browser are displayed in the console of Visual Studio Code.  -->  

<span data-ttu-id="38b77-138">Microsoft Visual Studio Code 拡張バージョン 1.1.4 用 [Microsoft Edge Developer Tools for Microsoft Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] では、各 DevTools インスタンスの横にファビコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-138">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.4 for Microsoft Visual Studio Code now displays a favicon next to each of the DevTools instances.</span></span>  <span data-ttu-id="38b77-139">Microsoft Edge からのコンソール メッセージが、**DevTools** コンソールの[Microsoft Visual Studio Code] の **[出力]** の下に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="38b77-139">Console messages from Microsoft Edge now display in the **DevTools Console** under **Output** of Microsoft Visual Studio Code.</span></span>  <span data-ttu-id="38b77-140">Microsoft Visual Studio Code は拡張機能を自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="38b77-140">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="38b77-141">バージョン 1.1.4 に手動で更新するには、[[拡張機能を手動で更新する]][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-141">To manually update to version 1.1.4, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  <span data-ttu-id="38b77-142">[vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools] GitHub リポジトリで問題をファイルし、拡張機能に貢献することができます。</span><span class="sxs-lookup"><span data-stu-id="38b77-142">You may file issues and contribute to the extension on the [vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools] GitHub repo.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="38b77-143">次の図は、Microsoft Edge の**コンソール** ツールにログインしている Web ページの例からのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="38b77-143">The following figure displays messages from an example webpage logged in the **Console** tool in Microsoft Edge.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="38b77-144">次の図は、**DevTools コンソール**の [Microsoft Visual Studio Code の**出力**] に記録されたサンプル Web ページからの同じメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="38b77-144">The following figure displays the same messages from the example webpage logged in the **DevTools Console** under **Output** of Microsoft Visual Studio Code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png" alt-text="Microsoft Edge DevTools のコンソールにメッセージを表示する" lightbox="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png":::
         <span data-ttu-id="38b77-146">Microsoft Edge DevTools のコンソールにメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="38b77-146">Display a message in Console in Microsoft Edge DevTools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png" alt-text="DevTools コンソールの [Microsoft Visual Studio Code の出力] の下に同じメッセージを表示します" lightbox="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png":::
         <span data-ttu-id="38b77-148">DevTools コンソールの [Microsoft Visual Studio Code の出力] の下に同じメッセージを表示します</span><span class="sxs-lookup"><span data-stu-id="38b77-148">Display the same message in the DevTools Console under Output of Microsoft Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-flexbox-editing-with-visual-flexbox-editor-and-multiple-overlays"></a><span data-ttu-id="38b77-149">ビジュアル フレックスボックス エディターと複数のオーバーレイによる CSS flexbox 編集の改善</span><span class="sxs-lookup"><span data-stu-id="38b77-149">Improved CSS flexbox editing with visual flexbox editor and multiple overlays</span></span>  

<!-- Title: Try different CSS flexbox layouts with the visual flexbox editor  -->  
<!-- Subtitle: In the Styles pane, choose the icon that appears next to display: flex to try different layout properties for flex containers.  -->  

<span data-ttu-id="38b77-150">DevTools には、専用の CSS flexbox デバッグ ツールが追加されています。</span><span class="sxs-lookup"><span data-stu-id="38b77-150">DevTools now has dedicated CSS flexbox debugging tools.</span></span>  <span data-ttu-id="38b77-151">`display: flex`または`display: inline-flex` CSS スタイルが HTML 要素に適用されている場合、**要素**ツールでその要素の横に`flex`アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-151">If the `display: flex` or `display: inline-flex` CSS style is applied to an HTML element, a `flex` icon displays next to that element in the **Elements** tool.</span></span>  <span data-ttu-id="38b77-152">Web ページにフレックス オーバーレイを表示\(または非表示\) するには、`flex`アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-152">To display \(or hide\) a flex overlay on the webpage, choose the `flex` icon.</span></span>  <span data-ttu-id="38b77-153">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issues [1166710][CR1166710] および [1175699][CR1175699]に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-153">To review the history of this feature in the Chromium open-source project, navigate to Issues [1166710][CR1166710] and [1175699][CR1175699].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="38b77-154">**Flexbox** エディターを開く場合は、**[スタイル]** ウィンドウに移動し、`display: flex` または `display: inline-flex` スタイルの横にある新しいアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-154">To open the **Flexbox** editor, navigate to the **Styles** pane and choose the new icon next to the `display: flex` or `display: inline-flex` style.</span></span>  <span data-ttu-id="38b77-155">**Flexbox** エディターでは、flexbox プロパティを簡単に編集できます。</span><span class="sxs-lookup"><span data-stu-id="38b77-155">The **Flexbox** editor provides a quick way to edit the flexbox properties.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="38b77-156">さらに、**[レイアウト]** ウィンドウの **[Flexbox]** セクションには、Web ページ上のすべての flexbox 要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-156">In addition, the **Flexbox** section in the **Layout** pane displays all of the flexbox elements on the webpage.</span></span>  <span data-ttu-id="38b77-157">各要素のオーバーレイを切り替えできます。</span><span class="sxs-lookup"><span data-stu-id="38b77-157">You may toggle the overlay of each element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-styles-display-flex-window.msft.png" alt-text="CSS flexbox デバッグ ツール" lightbox="../../media/2021/02/elements-styles-display-flex-window.msft.png":::
         <span data-ttu-id="38b77-159">CSS flexbox デバッグ ツール</span><span class="sxs-lookup"><span data-stu-id="38b77-159">CSS flexbox debugging tools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png" alt-text="[レイアウト] ウィンドウの [Flexbox] セクション" lightbox="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png":::
         <span data-ttu-id="38b77-161">**[レイアウト]** ウィンドウの **[Flexbox]** セクション</span><span class="sxs-lookup"><span data-stu-id="38b77-161">**Flexbox** section in the **Layout** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="keyboard-navigation-improvements-for-network-requests"></a><span data-ttu-id="38b77-162">ネットワーク要求のキーボード ナビゲーションの機能強化</span><span class="sxs-lookup"><span data-stu-id="38b77-162">Keyboard navigation improvements for network requests</span></span>  

<!-- Title: Navigate the request initiator chain in the Network tool with the keyboard  -->  
<!-- Subtitle: The Initiator pane may now be expanded or collapsed with the arrow keys.  -->  

<span data-ttu-id="38b77-163">以前は、**要素**ツールの DOM とは異なり、**イニシエーター** ウィンドウのキーボードの矢印キーを使用して、要求のチェーンを展開または折りたたむ機能が使えなくなっていました。</span><span class="sxs-lookup"><span data-stu-id="38b77-163">Previously, you were not able to expand or collapse the chain of requests using the arrow keys on the keyboard in the **Initiator** pane, unlike the DOM in the **Elements** tool.</span></span>  <span data-ttu-id="38b77-164">**ネットワーク** ツールでネットワーク要求を選択すると、**[イニシエーター]** ウィンドウに、現在選択されている要求を開始した要求のチェーンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-164">When a network request is selected in the **Network** tool, the **Initiator** pane displays the chain of requests that initiated the currently selected request.</span></span>  

<span data-ttu-id="38b77-165">Microsoft Edge バージョン 90 では、**イニシエーター** ウィンドウのキーボードの矢印キーを使用して、要求のチェーンを展開または折りたたみできます。</span><span class="sxs-lookup"><span data-stu-id="38b77-165">In Microsoft Edge version 90, you may expand or collapse the chain of requests using the arrow keys on the keyboard in the **Initiator** pane.</span></span>  <span data-ttu-id="38b77-166">チェーン内のフォーカスされたネットワーク要求も強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-166">The focused network request in the chain is also now highlighted.</span></span>  <span data-ttu-id="38b77-167">**ネットワーク** ツールのイニシエーターの詳細については、「[イニシエーターと依存関係の表示][DevtoolsNetworkReferenceDisplayInitiatorsDependencies]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-167">To learn more about initiators in the **Network** tool, navigate to [Display initiators and dependencies][DevtoolsNetworkReferenceDisplayInitiatorsDependencies].</span></span>  <span data-ttu-id="38b77-168">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issues [1158276][CR1158276] および [1160637][CR1160637]に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-168">To review the history of this feature in the Chromium open-source project, navigate to Issues [1158276][CR1158276] and [1160637][CR1160637].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain.msft.png" alt-text="ネットワーク要求を選択し、[イニシエーター] ウィンドウを選択します。" lightbox="../../media/2021/02/network-request-initiator-chain.msft.png":::
         <span data-ttu-id="38b77-170">ネットワーク要求を選択し、**[イニシエーター]** ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-170">Choose a Network request and choose the **Initiator** pane</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png" alt-text="要求開始チェーンを展開または折りたたみ、強調表示された行に従う" lightbox="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png":::
         <span data-ttu-id="38b77-172">要求開始チェーンを展開または折りたたみ、強調表示された行に従う</span><span class="sxs-lookup"><span data-stu-id="38b77-172">Expand or collapse the request initiator chain and follow the highlighted row</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="filtering-in-the-console-is-more-consistent"></a><span data-ttu-id="38b77-173">コンソールでのフィルター処理の整合性が高い</span><span class="sxs-lookup"><span data-stu-id="38b77-173">Filtering in the Console is more consistent</span></span>  

<!-- Title: Console improvements make filtering more consistent  -->  
<!-- Subtitle: The Log Levels dropdown is more clearly disabled when using filters in the Console sidebar.  -->  

<span data-ttu-id="38b77-174">[コンソール サイドバー][DevtoolsConsoleReferenceOpenConsoleSidebar]でフィルター 処理を行う場合、[[ログ レベル]][DevtoolsConsoleReferenceFilterByLogLevel] ドロップダウン のフィルターは 使用できません。</span><span class="sxs-lookup"><span data-stu-id="38b77-174">While you filter with the [Console Sidebar][DevtoolsConsoleReferenceOpenConsoleSidebar], the filters in the [Log Levels][DevtoolsConsoleReferenceFilterByLogLevel] dropdown are not available.</span></span>  <span data-ttu-id="38b77-175">以前は、**[コンソール サイドバー]** の フィルターが選択されている間でも、その上にマウス ポインターを置くと、**[ログ レベル]** ドロップダウン が 強調表示されました。</span><span class="sxs-lookup"><span data-stu-id="38b77-175">Previously, the **Log Levels** dropdown highlighted when you hovered on it, even while a filter from the **Console Sidebar** was chosen.</span></span>  <span data-ttu-id="38b77-176">Microsoft Edge バージョン 90では、**[コンソール サイドバー]** のフィルターが選択されている間に、その上にマウス ポインターを置くと、**[ログ レベル]** ドロップダウンが強調表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="38b77-176">In Microsoft Edge version 90, the **Log Levels** dropdown no longer highlights when you hover on it while a filter from the **Console Sidebar** is chosen.</span></span>  <span data-ttu-id="38b77-177">[コンソール][DevtoolsConsoleReferenceFilterMessages]でのフィルター処理の詳細については、「**メッセージのフィルター**」に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-177">To learn more about filtering in the **Console**, navigate to [Filter Messages][DevtoolsConsoleReferenceFilterMessages].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-old.msft.png" alt-text="以前は、[コンソール] サイドバーを開き、[既定のレベル] にカーソルを合わせると、強調表示されました" lightbox="../../media/2021/02/console-sidebar-default-levels-old.msft.png":::
         <span data-ttu-id="38b77-179">以前は、**[コンソール] サイドバー**を開き、**[既定のレベル]** にカーソルを合わせると強調表示されました</span><span class="sxs-lookup"><span data-stu-id="38b77-179">Previously, if you open the **Console sidebar** and hover on **Default levels** it was highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-new.msft.png" alt-text="Microsoft Edge 90 から、コンソール サイドバーを選択し、既定のレベルにカーソルを合わせると、強調表示されません" lightbox="../../media/2021/02/console-sidebar-default-levels-new.msft.png":::
         <span data-ttu-id="38b77-181">Microsoft Edge 90 から、**コンソール サイドバー**を選択し、**既定のレベル**にカーソルを合わせると、強調表示されません</span><span class="sxs-lookup"><span data-stu-id="38b77-181">Starting in Microsoft Edge 90, if you choose the **Console sidebar** and hover on **Default levels**, it does not highlight</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="38b77-182">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="38b77-182">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="the-console-now-escapes-double-quote-characters"></a><span data-ttu-id="38b77-183">コンソールで二重引用符をエスケープする</span><span class="sxs-lookup"><span data-stu-id="38b77-183">The Console now escapes double quote characters</span></span>  

<span data-ttu-id="38b77-184">以前は、**コンソール**は JavaScript 文字列で有効な二重引用符 \(`"`\) 文字を出力しませんでした。</span><span class="sxs-lookup"><span data-stu-id="38b77-184">Previously, the **Console** did not output valid double quote \(`"`\) characters in JavaScript strings.</span></span>  <span data-ttu-id="38b77-185">Microsoft Edge バージョン 90 から、**コンソール**はエスケープされた二重引用符 \(`"`\) 文字を使用して JavaScript 文字列を出力します。</span><span class="sxs-lookup"><span data-stu-id="38b77-185">Starting in Microsoft Edge version 90, the **Console** outputs JavaScript strings using escaped double quote \(`"`\) characters.</span></span>  <span data-ttu-id="38b77-186">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1178530][CR1178530] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-186">To review the history of this feature in the Chromium open-source project, navigate to Issue [1178530][CR1178530].</span></span>  

:::image type="complex" source="../../media/2021/02/console-string-formatted-double-quotes.msft.png" alt-text="コンソールは、エスケープされた二重引用符 (&#0022;) を使用して JavaScript 文字列を出力します。" lightbox="../../media/2021/02/console-string-formatted-double-quotes.msft.png":::
   <span data-ttu-id="38b77-188">**コンソール**は、 エスケープされた二重引用符 \(`"`\) 文字を使用して JavaScript 文字列を出力します。</span><span class="sxs-lookup"><span data-stu-id="38b77-188">The **Console** outputs JavaScript strings using escaped double quote \(`"`\) characters</span></span>  
:::image-end:::  

### <a name="emulate-the-css-color-gamut-media-feature"></a><span data-ttu-id="38b77-189">CSS 色域メディア機能をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="38b77-189">Emulate the CSS color-gamut media feature</span></span>  

<span data-ttu-id="38b77-190">[色域][ChromestatusFeature5354410980933632] メディア クエリは、ブラウザーとテスト中のデバイスでサポートされる色の概算範囲をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="38b77-190">The [color-gamut][ChromestatusFeature5354410980933632] media query emulates the approximate range of colors supported by the browser and the device you are testing.</span></span>  <span data-ttu-id="38b77-191">**[CSS メディア 機能の色域をエミュレートする]** のドロップダウンには、DevTools がエミュレートできる色空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38b77-191">The dropdown under **Emulate CSS media feature color-gamut** contains color spaces that DevTools may emulate.</span></span>  <span data-ttu-id="38b77-192">たとえば、`color-gamut: p3`メディア クエリをトリガーするには、ドロップダウンから **[色域: p3]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-192">For example, to trigger a `color-gamut: p3` media query, choose **color-gamut: p3** from the dropdown.</span></span>  

<span data-ttu-id="38b77-193">CSS 色域メディア機能をエミュレートするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="38b77-193">To emulate the CSS color-gamut media feature, complete the following actions.</span></span>  

1.  <span data-ttu-id="38b77-194">[コマンド メニュー][DevtoolsCommandMenuIndex] を開きます。</span><span class="sxs-lookup"><span data-stu-id="38b77-194">Open the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
1.  <span data-ttu-id="38b77-195">「`Rendering`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="38b77-195">Type `Rendering`.</span></span>  
1.  <span data-ttu-id="38b77-196">**[レンダリングの 表示]** コマンドを実行 します。</span><span class="sxs-lookup"><span data-stu-id="38b77-196">Run the **Show Rendering** command.</span></span>  
1.  <span data-ttu-id="38b77-197">**[CSS メディア 機能の色域をエミュレートする ]** に移動し、オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-197">Navigate to **Emulate CSS media feature color-gamut** and choose an option.</span></span>  

<span data-ttu-id="38b77-198">`color-gamut`この機能の詳細については、「[色の表示品質 : "色域" 機能][CsswgDraftsMediaqueries4ColorGamut]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-198">To learn more about the `color-gamut` feature, navigate to [Color Display Quality: the 'color-gamut' feature][CsswgDraftsMediaqueries4ColorGamut].</span></span>  <span data-ttu-id="38b77-199">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1073887][CR1073887] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-199">To review the history of this feature in the Chromium open-source project, navigate to Issue [1073887][CR1073887].</span></span>  

:::image type="complex" source="../../media/2021/02/rendering-css-color-gamut.msft.png" alt-text="CSS 色域メディア機能をエミュレートする" lightbox="../../media/2021/02/rendering-css-color-gamut.msft.png":::
   <span data-ttu-id="38b77-201">CSS 色域メディア機能をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="38b77-201">Emulate the CSS color-gamut media feature</span></span>  
:::image-end:::  

### <a name="improved-progressive-web-apps-tooling"></a><span data-ttu-id="38b77-202">プログレッシブ Web アプリのツールの改善</span><span class="sxs-lookup"><span data-stu-id="38b77-202">Improved Progressive Web Apps tooling</span></span>  

#### <a name="pwa-installability-warning-in-the-console"></a><span data-ttu-id="38b77-203">コンソールの PWA インストール可能性に関する警告</span><span class="sxs-lookup"><span data-stu-id="38b77-203">PWA installability warning in the Console</span></span>  

<span data-ttu-id="38b77-204">**コンソール** には、 [プログレッシブ Web アプリのオフライン サポート検出の改善][ChromeDeveloperBlogImprovedPwaOfflineDetection]へのリンクを含む、より詳細な[プログレッシブ Web アプリ (PWA)][ProgressiveWebAppsIndex] インストール可能性の警告メッセージ が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-204">The **Console** now displays a more detailed [Progressive Web Apps (PWA)][ProgressiveWebAppsIndex] installability warning message with a link to [Improving Progressive Web App offline support detection][ChromeDeveloperBlogImprovedPwaOfflineDetection].</span></span>  

:::image type="complex" source="../../media/2021/02/console-pwa-installability.msft.png" alt-text="コンソール ツールでの PWA インストール可能性の警告" lightbox="../../media/2021/02/console-pwa-installability.msft.png":::
   <span data-ttu-id="38b77-206">**コンソール** ツールでの PWA インストール可能性の警告</span><span class="sxs-lookup"><span data-stu-id="38b77-206">PWA installability warning in **Console** tool</span></span>  
:::image-end:::  

#### <a name="pwa-description-length-warning-in-the-manifest-pane"></a><span data-ttu-id="38b77-207">マニフェスト ウィンドウの PWA の説明の長さの警告</span><span class="sxs-lookup"><span data-stu-id="38b77-207">PWA description length warning in the Manifest pane</span></span>

<span data-ttu-id="38b77-208">**マニフェスト** の説明が 324 文字を超えると、マニフェスト ウィンドウに警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-208">The **Manifest** pane now displays a warning message if the manifest description exceeds 324 characters.</span></span>  

:::image type="complex" source="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png" alt-text="PWA の説明の切り捨て警告" lightbox="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png":::
   <span data-ttu-id="38b77-210">PWA の説明の切り捨て警告</span><span class="sxs-lookup"><span data-stu-id="38b77-210">PWA description truncate warning</span></span>  
:::image-end:::  

<span data-ttu-id="38b77-211">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [965802][CR965802]、[1146450][CR1146450]、および [1169689][CR1169689] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-211">To review the history of this feature in the Chromium open-source project, navigate to Issues [965802][CR965802], [1146450][CR1146450], and [1169689][CR1169689].</span></span>  

### <a name="new-remote-address-space-column-in-the-network-tool"></a><span data-ttu-id="38b77-212">[ネットワーク] ツールの [新しいリモート アドレス空間] 列</span><span class="sxs-lookup"><span data-stu-id="38b77-212">New Remote Address Space column in the Network tool</span></span>  

<!-- does not work in canary 90.0.813.0 -->  
<span data-ttu-id="38b77-213">新しい **[リモート アドレス空間]** 列には、各ネットワーク リソースのネットワーク IP アドレス空間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-213">The new **Remote Address Space** column displays the network IP address space of each network resource.</span></span>  <span data-ttu-id="38b77-214">新しい [リモート アドレス空間] 列を表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="38b77-214">To display the new Remote Address Space column, complete the following actions.</span></span>  

1.  <span data-ttu-id="38b77-215">**[ネットワーク]** ツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-215">Navigate to the **Network** tool.</span></span>  
1.  <span data-ttu-id="38b77-216">[要求] テーブルで、ヘッダー行にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="38b77-216">In the Requests table, hover on the header row, and open the contextual menu \(right-click\).</span></span>  <span data-ttu-id="38b77-217">[要求] テーブルから列を追加または削除する方法については、「[列の追加または削除][DevtoolsNetworkReferenceAddRemoveColumns]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-217">To learn how to add or remove columns from the Requests table, navigate to [Add or remove columns][DevtoolsNetworkReferenceAddRemoveColumns].</span></span>  
1.  <span data-ttu-id="38b77-218">**[リモート アドレス空間]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-218">Choose **Remote Address Space**.</span></span>  
    
<span data-ttu-id="38b77-219">Requests テーブルに、**[リモート アドレス空間]** という名前のヘッダーを含む新しい列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-219">The Requests table now displays a new column with the header named **Remote Address Space**.</span></span>  <span data-ttu-id="38b77-220">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1128885][CR1128885] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-220">To review the history of this feature in the Chromium open-source project, navigate to Issue [1128885][CR1128885].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png" alt-text="コンテキスト メニューで、[リモート アドレス空間] を選択します。" lightbox="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png":::
         <span data-ttu-id="38b77-222">コンテキスト メニューで、**[リモート アドレス空間]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-222">In the contextual menu, choose the **Remote Address Space**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-remote-address-space.msft.png" alt-text="[要求] テーブルに [リモート アドレス空間] 列が表示される" lightbox="../../media/2021/02/network-requests-remote-address-space.msft.png":::
         <span data-ttu-id="38b77-224">[要求] テーブルに **[リモート アドレス空間]** 列が表示される</span><span class="sxs-lookup"><span data-stu-id="38b77-224">The Requests table now displays the **Remote Address Space** column</span></span> :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-allowed-and-disallowed-features-in-the-frame-details-view"></a><span data-ttu-id="38b77-225">[フレームの詳細] ビューに許可および禁止された機能を表示する</span><span class="sxs-lookup"><span data-stu-id="38b77-225">Display allowed and disallowed features in the Frame details view</span></span>  

<span data-ttu-id="38b77-226">[[フレームの詳細]][GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer] ビューに、アクセス許可ポリシーによって制御される許可および禁止されたブラウザー機能の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-226">The Frame details view now displays a list of allowed and disallowed browser features controlled by the [Permissions Policy][GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer].</span></span>  <span data-ttu-id="38b77-227">アクセス許可ポリシーは Web プラットフォーム API で、Web ページ内のブラウザー機能を個々のフレームまたは埋め込み iframe 内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38b77-227">Permissions Policy is a web platform API that allows \(or blocks\) a webpage the use of browser features in an individual frame or in iframes that it embeds.</span></span>  <span data-ttu-id="38b77-228">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1158827][CR1158827] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-228">To review the history of this feature in the Chromium open-source project, navigate to Issue [1158827][CR1158827].</span></span>  

:::image type="complex" source="../../media/2021/02/application-frames-permissions-policy.msft.png" alt-text="アクセス許可ポリシーに基づく許可機能と禁止機能" lightbox="../../media/2021/02/application-frames-permissions-policy.msft.png":::
   <span data-ttu-id="38b77-230">アクセス許可ポリシーに基づく許可機能と禁止機能</span><span class="sxs-lookup"><span data-stu-id="38b77-230">Allowed and disallowed features based on the Permission Policy</span></span>  
:::image-end:::  

### <a name="new-sameparty-column-in-the-cookies-pane"></a><span data-ttu-id="38b77-231">Cookie ウィンドウの新しい SameParty 列</span><span class="sxs-lookup"><span data-stu-id="38b77-231">New SameParty column in the Cookies pane</span></span>  

<span data-ttu-id="38b77-232">**アプリケーション** ツールの **[Cookie]** ウィンドウ に、各 Cookie の `SameParty` 属性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-232">The **Cookies** pane in the **Application** tool now displays the `SameParty` attribute for each cookie.</span></span>  <span data-ttu-id="38b77-233">この `SameParty` 属性は、Cookie が同じ[ファースト パーティ セット][GithubPrivacycgFirstPartySets]の起点への要求に含まれているかどうかを示す新しいブール属性 です。</span><span class="sxs-lookup"><span data-stu-id="38b77-233">The `SameParty` attribute is a new boolean attribute to indicate whether a cookie is included in requests to origins of the same [First-Party Sets][GithubPrivacycgFirstPartySets].</span></span>  <span data-ttu-id="38b77-234">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1161427][CR1161427] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-234">To review the history of this feature in the Chromium open-source project, navigate to Issue [1161427][CR1161427].</span></span>  

:::image type="complex" source="../../media/2021/02/application-storage-cookies-sameparty.msft.png" alt-text="Cookie ウィンドウの SameParty 列" lightbox="../../media/2021/02/application-storage-cookies-sameparty.msft.png":::
   <span data-ttu-id="38b77-236">**Cookie** ウィンドウの **SameParty** 列</span><span class="sxs-lookup"><span data-stu-id="38b77-236">**SameParty** column in the **Cookies** pane</span></span>  
:::image-end:::  

### <a name="fndisplayname-property-in-the-console-tool-is-now-deprecated"></a><span data-ttu-id="38b77-237">コンソール ツールの fn.displayName プロパティが廃止されました</span><span class="sxs-lookup"><span data-stu-id="38b77-237">fn.displayName property in the Console tool is now deprecated</span></span>  

<span data-ttu-id="38b77-238">以前は、`fn.displayName` プロパティを使用して、`error.stack` および DevTools スタック トレースに表示する関数のデバッグ名を制御できました。</span><span class="sxs-lookup"><span data-stu-id="38b77-238">Previously, the `fn.displayName` property allowed you to control debug names for functions to display in `error.stack` and in DevTools stack traces.</span></span>  <span data-ttu-id="38b77-239">Microsoft Edge バージョン90以降、`fn.displayName` プロパティは非推奨になり、`fn.name` プロパティに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="38b77-239">Starting in Microsoft Edge version 90, the `fn.displayName` property is now deprecated, and replaced by the `fn.name` property.</span></span>  <span data-ttu-id="38b77-240">標準の`Object.defineProperty`メソッドを使用して`fn.name`プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="38b77-240">Use the standard `Object.defineProperty` method to define the `fn.name` property.</span></span>  <span data-ttu-id="38b77-241">`fn.name` の詳細については、[Function.name][MdnJavascriptReferenceGlobalObjectsFunctionName] に移動してください。</span><span class="sxs-lookup"><span data-stu-id="38b77-241">To learn more about `fn.name`, navigate to [Function.name][MdnJavascriptReferenceGlobalObjectsFunctionName].</span></span>  <span data-ttu-id="38b77-242">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1177685][CR1177685] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-242">To review the history of this feature in the Chromium open-source project, navigate to Issue [1177685][CR1177685].</span></span>  

:::image type="complex" source="../../media/2021/02/console-display-name-name.msft.png" alt-text="関数のデバッグ名を制御するための fn.name プロパティの例" lightbox="../../media/2021/02/console-display-name-name.msft.png":::
   <span data-ttu-id="38b77-244">関数のデバッグ名を制御するための `fn.name` プロパティの例</span><span class="sxs-lookup"><span data-stu-id="38b77-244">An example of the `fn.name` property to control debug names for functions</span></span>  
:::image-end:::  

### <a name="full-accessibility-tree-view-in-the-elements-tool"></a><span data-ttu-id="38b77-245">要素ツールの完全なアクセシビリティ ツリー ビュー</span><span class="sxs-lookup"><span data-stu-id="38b77-245">Full accessibility tree view in the Elements tool</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="38b77-246">この実験では、**要素** ツールで**アクセシビリティ ツリー ビュー全体**を提供します。</span><span class="sxs-lookup"><span data-stu-id="38b77-246">This experiment provides a **full accessibility tree view** in the **Elements** tool.</span></span>  <span data-ttu-id="38b77-247">[[アクセシビリティ]][DevtoolsAccessibilityReferenceTheAccessibilityPane] ウィンドウ には部分的なアクセシビリティ ツリー ビューが表示され、ルート ノードから検査されたノードへの直接の祖先チェーンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b77-247">The [Accessibility][DevtoolsAccessibilityReferenceTheAccessibilityPane] pane provides a partial accessibility tree view, that displays the direct ancestor chain from the root node to the inspected node.</span></span>  
<span data-ttu-id="38b77-248">この実験を有効にし、DevTools を再読み込みした後、次のいずれかのボタンを選択して、Web ページ上のすべての要素の [要素] ツールの表示を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="38b77-248">After you turn on this experiment and reload the DevTools, choose one of the following buttons to switch the display in the Elements tool for all elements on the webpage.</span></span>  

*   <span data-ttu-id="38b77-249">完全なアクセシビリティ ツリー ビューを表示するには、**[アクセシビリティ ツリーに切り替える]** ビューを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-249">To display the full accessibility tree view , choose the **Switch to Accessibility Tree view**.</span></span>  
*   <span data-ttu-id="38b77-250">DOM ツリー ビューを表示するには、**[DOM ツリー ビューに切り替える]** ビューを選択します。</span><span class="sxs-lookup"><span data-stu-id="38b77-250">To display the DOM tree view, choose the **Switch to DOM Tree view**.</span></span>  
    
<span data-ttu-id="38b77-251">試験を有効にするには、[[試験的機能を有効にする]][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] に移動し、[要素] ウィンドウの **[完全なアクセシビリティ ツリー ビューを有効にする]** の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="38b77-251">To turn on the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] and choose the checkbox next to **Enable full accessibility tree view in Elements pane**.</span></span>  <span data-ttu-id="38b77-252">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [887173][CR887173] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38b77-252">To review the history of this feature in the Chromium open-source project, navigate to Issue [887173][CR887173].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png" alt-text="DOM ツリー ビューを表示する" lightbox="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png":::
         <span data-ttu-id="38b77-254">**DOM ビュー** を表示する</span><span class="sxs-lookup"><span data-stu-id="38b77-254">Display the **DOM view**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png" alt-text="アクセシビリティ ツリービュー全体を表示する" lightbox="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png":::
         <span data-ttu-id="38b77-256">**[完全なアクセシビリティ ツリー]** ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="38b77-256">Display the **Full Accessibility Tree view**</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="38b77-257">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="38b77-257">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="38b77-258">Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="38b77-258">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="38b77-259">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="38b77-259">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="38b77-260">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="38b77-260">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsAccessibilityReferenceTheAccessibilityPane]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#the-accessibility-pane "アクセシビリティ ウィンドウ - アクセシビリティ リファレンス | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterByLogLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "ログ レベルによるフィルター - コンソール リファレンス | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterMessages]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-messages "フィルター メッセージ - コンソール リファレンス | Microsoft Docs"  
[DevtoolsConsoleReferenceOpenConsoleSidebar]: /microsoft-edge/devtools-guide-chromium/console/reference#open-the-console-sidebar "コンソール サイドバーを開く - コンソール リファレンス | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexEnablePlusButtonTabMenusToOpenMoreTools]: /microsoft-edge/devtools-guide-chromium/experimental-features/index#enable--button-tab-menus-to-open-more-tools "[+] ボタン タブ メニューを有効にして、その他のツールを開く - 試験的な| Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features/index#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsNetworkReferenceAddRemoveColumns]: /microsoft-edge/devtools-guide-chromium/network/reference#add-or-remove-columns "列の追加または削除 - ネットワーク分析リファレンス | Microsoft Docs"  
[DevtoolsNetworkReferenceDisplayInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#display-initiators-and-dependencies "イニシエーターと依存関係の表示 - ネットワーク分析リファレンス | Microsoft Docs"  

[ProgressiveWebAppsIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプログレッシブ Web アプリの概要 | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 マーケットプレース | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  

[ChromeDeveloperBlogImprovedPwaOfflineDetection]: https://developer.chrome.com/blog/improved-pwa-offline-detection "プログレッシブ Web アプリのオフライン サポート検出の改善 | Chrome 開発者"  

[ChromestatusFeature5354410980933632]: https://www.chromestatus.com/feature/5354410980933632 "色域メディア クエリ | Chrome プラットフォーム ステータス"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  
[CR174309]: https://crbug.com/174309 "問題 174309: DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium のバグ"  
[CR887173]: https://crbug.com/887173 "問題 887173: DevTools: 完全なアクセシビリティ ツリーの検査 | Chromium のバグ"  
[CR965802]: https://crbug.com/965802 "問題 965802: より正確な Service Worker のオフライン機能検出を実装する | Chromium のバグ"  
[CR1073887]: https://crbug.com/1073887 "問題 1073887: DevTools: @media (color-gamut: ...) 色空間エミュレーション | Chromium のバグ"  
[CR1128885]: https://crbug.com/1128885 "問題 1128885: CORS の DevTools サポート - RFC1918 | Chromium のバグ"  
[CR1146450]: https://crbug.com/1146450 "問題 1146450: [Android] ボトムシートのインストールを実装する | Chromium のバグ"  
[CR1158276]: https://crbug.com/1158276 "問題 1158276: DevTools | の [ネットワーク] セクションの矢印キーを使用して [イニシエーター チェーンの要求] ウィンドウを展開/契約する | クロムのバグ"  
[CR1158827]: https://crbug.com/1158827 "問題 1158827: [アクセス許可ポリシー] アクセス許可ポリシーの devtool サポートを実装する | Chromium のバグ"  
[CR1160637]: https://crbug.com/1160637 "問題 1160637: 「開発ツール」ウィンドウの「ネットワーク」セクションで「リクエスト イニシエーター チェーン」へのフォーカスが不完全であることがわかる | Chromium のバグ"  
[CR1161427]: https://crbug.com/1161427 "問題1161427: &#9730; DevTools でSame Party Cookie 属性のデバッグをサポートする | Chromium のバグ"  
[CR1166710]: https://crbug.com/1166710 "問題 1166710: デフォルトで flexbox ツールの実験を有効にする | Chromium のバグ"  
[CR1169689]: https://crbug.com/1169689 "問題 1169689: PWA インストールのボトム シートにカテゴリを含めるべきではない | Chromium のバグ"  
[CR1175699]: https://crbug.com/1175699 "問題 1175699: Flexbox エディター | Chromium のバグ"  
[CR1177685]: https://crbug.com/1177685 "問題 1177685: 標準以外の fn.displayName サポート を削除する | Chromium のバグ"  
[CR1178530]: https://crbug.com/1178530 "問題 1178530: 文字列を印刷するときにコンソールが二重引用符をエスケープしない | Chromium のバグ"  

[CsswgDraftsMediaqueries4ColorGamut]: https://drafts.csswg.org/mediaqueries-4#color-gamut "カラー表示品質：「色域」機能 | CSS ワーキング グループ エディター ドラフト"  

[GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/main/DevTools/FocusMode/explainer.md "DevTools: フォーカス モード UI - MicrosoftEdge/MSEdgeExplainers | GitHub"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubPrivacycgFirstPartySets]: https://github.com/privacycg/first-party-sets "ファーストパーティ セット | GitHub"  

[GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "アクセス許可ポリシーの説明| GitHub"  

[MdnJavascriptReferenceGlobalObjectsFunctionName]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Function/name "Function.name | MDN"  

> [!NOTE]
> <span data-ttu-id="38b77-300">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="38b77-300">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="38b77-301">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2021/02/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="38b77-301">The original page is found [here](https://developers.google.com/web/updates/2021/02/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="38b77-303">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="38b77-303">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
