---
description: 新機能ツールが Welcome になりました。[スタイル] ウィンドウの Visual Font Editor、CSS Flexbox デバッグ ツールなど。
title: DevTools の新機能 (Microsoft Edge 89)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.localizationpriority: high
ms.openlocfilehash: ec14d802af52c0bb2e658549f48764279c787f47
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514369"
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
# <a name="whats-new-in-devtools-microsoft-edge-89"></a><span data-ttu-id="eafdc-104">DevTools の新機能 (Microsoft Edge 89)</span><span class="sxs-lookup"><span data-stu-id="eafdc-104">What's New In DevTools (Microsoft Edge 89)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="whats-new-is-now-welcome"></a><span data-ttu-id="eafdc-105">新機能が Welcome になりました</span><span class="sxs-lookup"><span data-stu-id="eafdc-105">What's New is now Welcome</span></span>  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="eafdc-106">Microsoft Edge DevTools の **新機能** ツールに新しい外観と新しい名前ができあがりました:  **Welcome**。</span><span class="sxs-lookup"><span data-stu-id="eafdc-106">The **What's New** tool in the Microsoft Edge DevTools now has a new appearance and a new name:  **Welcome**.</span></span>  <span data-ttu-id="eafdc-107">**Welcome** ツールでは、最新の DevTools ニュースと更新プログラムが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-107">The **Welcome** tool still displays the latest DevTools news and updates.</span></span>  <span data-ttu-id="eafdc-108">また、Microsoft Edge DevTools のドキュメントへのリンク、フィードバックの送信方法なども含まれています。</span><span class="sxs-lookup"><span data-stu-id="eafdc-108">It now also includes links to Microsoft Edge DevTools documentation, ways to submit feedback, and more.</span></span>  <span data-ttu-id="eafdc-109">Microsoft Edge への更新後 **Welcome** ツールを表示するには、タイトルで **更新ごとにタブを開く** の横にあるチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-109">To display the **Welcome** tool after each update to Microsoft Edge, choose the checkbox next to **Open tab after each update** under the title.</span></span>  <span data-ttu-id="eafdc-110">**Welcome** ツールを閉じるには、タブ タイトルの右側にある **[X]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-110">To close the **Welcome** tool, choose the **X** on the right-side of the tab title.</span></span>  <span data-ttu-id="eafdc-111">元の **新機能** ツールを使用する場合は、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**Welcome タブを有効にする** の横にあるチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-111">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="Welcome ツールが強調表示されます" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   <span data-ttu-id="eafdc-113">**Welcome** ツールが強調表示されます</span><span class="sxs-lookup"><span data-stu-id="eafdc-113">The **Welcome** tool is highlighted</span></span>  
:::image-end:::  

## <a name="visual-font-editor-in-the-styles-pane"></a><span data-ttu-id="eafdc-114">[スタイル] ウィンドウの Visual Font Editor</span><span class="sxs-lookup"><span data-stu-id="eafdc-114">Visual Font Editor in the Styles pane</span></span>  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="eafdc-115">CSS でフォントを使用する場合は、新しい Visual [Font Editor][DevtoolsInspectStylesEditFonts] を使用します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-115">When you work with fonts in CSS, use the new visual [Font Editor][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="eafdc-116">フォールバック フォントを定義しスライダーを使用して、フォントの太さ、サイズ、線の高さ、間隔を定義できます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-116">You may define fallback fonts, and use sliders to define font weight, size, line-height, and spacing.</span></span>  <span data-ttu-id="eafdc-117">**Font Editor** を使用すると次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-117">The **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="eafdc-118">異なるフォント プロパティの単位を切り替える</span><span class="sxs-lookup"><span data-stu-id="eafdc-118">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="eafdc-119">異なるフォント プロパティのキーワードを切り替える</span><span class="sxs-lookup"><span data-stu-id="eafdc-119">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="eafdc-120">単位を変換</span><span class="sxs-lookup"><span data-stu-id="eafdc-120">Convert units</span></span>  
*   <span data-ttu-id="eafdc-121">正確な CSS コードを生成</span><span class="sxs-lookup"><span data-stu-id="eafdc-121">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="eafdc-122">この実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**[スタイル] ウィンドウ内の Visual Font Editor ツールを有効にする** の横にあるチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-122">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new Font Editor tools within Styles pane**.</span></span>  <span data-ttu-id="eafdc-123">詳細については、[DevTools の [スタイル] ウィンドウで CSS フォント スタイルと設定を編集][DevtoolsInspectStylesEditFonts] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-123">For more information, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="eafdc-124">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1093229][CR1093229] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-124">To review the history of this feature in the Chromium open-source project, navigate to Issue [1093229][CR1093229].</span></span>  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="[スタイル] ウィンドウで Visual Font Editor が強調表示されます" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   <span data-ttu-id="eafdc-126">**スタイル** ウィンドウで Visual **Font Editor** が強調表示されます</span><span class="sxs-lookup"><span data-stu-id="eafdc-126">The visual **Font editor** is highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="css-flexbox-debugging-tools"></a><span data-ttu-id="eafdc-127">CSS Flexbox デバッグ ツール</span><span class="sxs-lookup"><span data-stu-id="eafdc-127">CSS Flexbox debugging tools</span></span>  

<span data-ttu-id="eafdc-128">Flexbox のデバッグ機能は、開発途中です。</span><span class="sxs-lookup"><span data-stu-id="eafdc-128">Flexbox debugging features are in active development.</span></span>  <span data-ttu-id="eafdc-129">次の 2 つの機能の実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**新しい CSS Flexbox デバッグ機能を有効にする** の横にあるチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-129">To turn on the experiment for the following two features, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new CSS Flexbox debugging features**.</span></span>  <span data-ttu-id="eafdc-130">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1136394][CR1136394] と [1139949][CR1139949] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-130">To review the history of this feature in the Chromium open-source project, navigate to Issues [1136394][CR1136394] and [1139949][CR1139949].</span></span>  

### <a name="new-flexbox-flex-icon-helps-identify-and-display-flex-containers"></a><span data-ttu-id="eafdc-131">新しい Flexbox (flex) アイコンを使用すると、flex コンテナーの識別と表示ができます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-131">New Flexbox (flex) icon helps identify and display flex containers</span></span>  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="eafdc-132">**要素** ツールで、新しい Flexbox (flex) アイコンを使用すると、コード内の Flexbox コンテナーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-132">In the **Elements** tool, the new Flexbox (flex) icon helps you identify Flexbox containers in your code.</span></span>  <span data-ttu-id="eafdc-133">Flexbox \(flex\) アイコンを選択すると、Flexbox コンテナーのアウトラインを示すオーバーレイ効果を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-133">Choose the Flexbox \(flex\) icon to turn on or off the overlay effect that outlines a Flexbox container.</span></span>  <span data-ttu-id="eafdc-134">**スタイル** ウィンドウと **計算済み** ウィンドウの横にある**レイアウト** ウィンドウでオーバーレイの色をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-134">You may customize the color of the overlay in the **Layout** pane, which is located next to **Styles** and **Computed**.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="eafdc-135">Flexbox コンテナーのアウトラインを示すオーバーレイ効果を有効または無効にするには、Flexbox \(`flex`\) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-135">To turn on and off the overlay effect that outlines the Flexbox container, choose the Flexbox \(`flex`\) icon.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="eafdc-136">**スタイル** ウィンドウと **計算済み** ウィンドウの横にある**レイアウト** ウィンドウでオーバーレイの色をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-136">You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (flex) アイコンと Web ページを強調表示しました" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         <span data-ttu-id="eafdc-138">**Flexbox** \(`flex`\) アイコンと Web ページを強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-138">The **Flexbox** \(`flex`\) icon and webpage highlighted</span></span> :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="Flexbox オーバーレイをレイアウト ウィンドウで強調表示しました" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         <span data-ttu-id="eafdc-140">**Flexbox オーバーレイ** を **レイアウト** ウィンドウで強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-140">The **Flexbox overlays** highlighted in the **Layout** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-alignment-icons-and-visual-guides-when-flexbox-layouts-change-using-css-properties"></a><span data-ttu-id="eafdc-141">CSS プロパティを使用して Flexbox レイアウトが変更された場合に配置アイコンとビジュアル ガイドを表示する</span><span class="sxs-lookup"><span data-stu-id="eafdc-141">Display alignment icons and visual guides when Flexbox layouts change using CSS properties</span></span>  

<!--  Title: Display alignment icons and visual guides for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="eafdc-142">Flexbox レイアウトの CSS を編集すると、関連する Flexbox プロパティの横に便利なアイコンが表示されるようになった **スタイル** ウィンドウで CSS のオートコンプリートが行われます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-142">When you edit CSS for your Flexbox layout, CSS autocompletes in the **Styles** pane now displays helpful icons next to relevant Flexbox properties.</span></span>  <span data-ttu-id="eafdc-143">この新機能を試す場合は、**要素** ツールを開き任意の flex コンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-143">To try this new feature, open the **Elements** tool and select a flex container.</span></span>  <span data-ttu-id="eafdc-144">次に、**スタイル** ウィンドウでそのコンテナーに任意のプロパティを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-144">Then add or change a property on that container in the **Styles** pane.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="eafdc-145">オートコンプリート メニューには、`align-content` や `align-items` のような配置プロパティの効果を示すアイコンが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-145">The autocomplete menu now displays icons that indicate the effect of alignment properties such as `align-content` and `align-items`.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="eafdc-146">さらに、DevTools には ガイドラインが表示され、`align-items` CSS プロパティを詳細に確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-146">Additionally, DevTools now displays a guiding line to help you better review the `align-items` CSS property.</span></span>  <span data-ttu-id="eafdc-147">`gap` CSS プロパティもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eafdc-147">The `gap` CSS property is supported as well.</span></span>  <span data-ttu-id="eafdc-148">次の図では、`gap` CSS プロパティが `gap: 12px;` に設定され、各ギャップのハッチング パターンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-148">In the following figure, the `gap` CSS property is set to `gap: 12px;` and the hatching pattern for each gap is displayed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="align- で始まる CSS プロパティへのオートコンプリート メニューを強調表示しました" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         <span data-ttu-id="eafdc-150">CSS プロパティへのオートコンプリート メニューを強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-150">Autocomplete menu highlighted for CSS properties that start with</span></span> `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS プロパティと Web ページの Flexbox ギャップを強調表示しました" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         <span data-ttu-id="eafdc-152">CSS プロパティと Web ページの Flexbox `gap` を強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-152">Flexbox `gap` in CSS properties and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="add-tools-quickly-with-new-more-tools-button"></a><span data-ttu-id="eafdc-153">新しい [その他のツール] ボタンを使用してツールをすばやく追加</span><span class="sxs-lookup"><span data-stu-id="eafdc-153">Add tools quickly with new More Tools button</span></span>  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="eafdc-154">これで、他のツールを Microsoft Edge DevTools で開く新しい方法が使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-154">You now have a new way to open more tools in the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="eafdc-155">この実験を有効にすると、**その他のツール** アイコンは、メイン パネルの右側にプラス記号 ( `+` ) で表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-155">After you turn on this experiment, the **More Tools** icon displays as a plus sign (`+`) to the right of the main panel.</span></span>  <span data-ttu-id="eafdc-156">メイン パネルに追加する他のツールの一覧を表示するには、**その他のツール** \(`+`\) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-156">To display a list of other tools to add to the main panel, choose the **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="eafdc-157">この実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**+ ボタン タブ メニューを有効にしてその他のツールを開く** の横にあるチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-157">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**, and then choose the checkbox next to **Enable + button tab menus to open more tools**.</span></span>  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="その他のツールを DevTools で強調表示しました" lightbox="../../media/2021/01/more-tools.msft.png":::
   <span data-ttu-id="eafdc-159">**その他のツール** を DevTools で強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-159">**More Tools** highlighted in DevTools</span></span>  
:::image-end:::  

## <a name="assistive-technologies-now-announce-position-and-count-of-css-suggestions"></a><span data-ttu-id="eafdc-160">支援技術では CSS 候補の位置と数を発表しています</span><span class="sxs-lookup"><span data-stu-id="eafdc-160">Assistive technologies now announce position and count of CSS suggestions</span></span>  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

<span data-ttu-id="eafdc-161">CSS を編集すると、機能のドロップダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-161">When you edit CSS, you get a dropdown of features.</span></span>  <span data-ttu-id="eafdc-162">この機能は Microsoft Edge バージョン 89 で発表されているので、支援技術のユーザーは利用できません。</span><span class="sxs-lookup"><span data-stu-id="eafdc-162">This feature was not available to users of assistive technologies, since it is announced in Microsoft Edge version 89.</span></span>  <span data-ttu-id="eafdc-163">支援技術のユーザーは、**スタイル** ウィンドウで CSS 候補に移動できます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-163">A user of assistive technologies may now navigate CSS suggestions in the **Styles** pane.</span></span>  <span data-ttu-id="eafdc-164">Microsoft Edge バージョン 88 以前には、**スタイル** ウィンドウで CSS を編集する場合、支援技術で候補リストから移動したユーザーを `Suggestion` と表現していました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-164">In Microsoft Edge version 88 and earlier, assistive technology announced `Suggestion` as a user navigated through the list of suggestions when editing CSS in the **Styles** pane.</span></span>  <span data-ttu-id="eafdc-165">Microsoft Edge バージョン 89 では、支援技術のユーザーが現在の提案の位置と数を確かめることがきます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-165">In Microsoft Edge version 89, a user of assistive technology now hears the position and count of the current suggestion.</span></span>  <span data-ttu-id="eafdc-166">各提案では、候補リストから移動したユーザーを提案 3/5 などのように表現しています。</span><span class="sxs-lookup"><span data-stu-id="eafdc-166">Each suggestion is announced as the user navigates through the list of suggestions, such as Suggestion 3 of 5.</span></span>  <span data-ttu-id="eafdc-167">DevTools での CSS 記述方法に関するの詳細は、[CSS を変更][DevtoolsCssReferenceChangeCss] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-167">To learn more about writing CSS in the DevTools, navigate to [Change CSS][DevtoolsCssReferenceChangeCss].</span></span>  <span data-ttu-id="eafdc-168">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1157329][CR1157329]に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-168">To review the history of this feature in the Chromium open-source project, navigate to Issue [1157329][CR1157329].</span></span>  

<span data-ttu-id="eafdc-169">この実験を有効にした状態で、ビデオで提案を表示しながら読み上げを聞くには、YouTube で [devtools オプションのボイスオーバー](https://youtu.be/9TcUpleEwwA) に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-169">To view a video that displays and reads aloud several suggestions with this experiment turned on, navigate to [Voiceover announcing devtools options](https://youtu.be/9TcUpleEwwA) on YouTube.</span></span>  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text="候補を [スタイル] ウィンドウで強調表示しました" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   <span data-ttu-id="eafdc-171">`suggestion` リストを **スタイル** ウィンドウで強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-171">The `suggestion` list highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a><span data-ttu-id="eafdc-172">Surface Duo と Samsung Galaxy Fold のエミュレート</span><span class="sxs-lookup"><span data-stu-id="eafdc-172">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

<span data-ttu-id="eafdc-173">Microsoft Edge の次のデバイスで、Web サイトの外観やアプリの外観をテストします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-173">Test the appearance of your website or app on the following devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="eafdc-174">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="eafdc-174">Surface Duo</span></span>][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [<span data-ttu-id="eafdc-175">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="eafdc-175">Samsung Galaxy Fold</span></span>][SamsungUsMobileGalaxyFold]  
    
<span data-ttu-id="eafdc-176">**実験用 Web プラットフォーム機能をオン** にし、新しい [CSS メディアの画面スパン機能][DualScreenWebCssMediaSpanning] と [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments] にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-176">Turn on **Experimental Web Platform features** to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments].</span></span>  <span data-ttu-id="eafdc-177">`edge://flags` まで移動し、**実験用 Web プラットフォーム機能** 横にあるフラグの設定を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-177">Navigate to `edge://flags` and toggle the flag next to **Experimental Web Platform features**.</span></span>  <span data-ttu-id="eafdc-178">デュアルスクリーン デバイスと折りたたみ式デバイスのために Web サイトやアプリを強化するには、[デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-178">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="eafdc-179">[スパニング][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: Web サイト (またはアプリ) が両方の画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-179">[Spanning][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>  
*   <span data-ttu-id="eafdc-180">[シームのレンダリング][DualScreenIntroductionHowToWorkWithSeam]: シームとは、2 つの画面の間の領域のことです。</span><span class="sxs-lookup"><span data-stu-id="eafdc-180">[Rendering the seam][DualScreenIntroductionHowToWorkWithSeam], which is the space between the two screens.</span></span>  
    
<span data-ttu-id="eafdc-181">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1054281][CR1054281] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-181">To review the history of this feature in the Chromium open-source project, navigate to Issue [1054281][CR1054281].</span></span>  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="デュアルスクリーンをエミュレート" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   <span data-ttu-id="eafdc-183">デュアルスクリーンをエミュレート</span><span class="sxs-lookup"><span data-stu-id="eafdc-183">Emulate dual-screen</span></span>  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-112"></a><span data-ttu-id="eafdc-184">Visual Studio Code バージョン 1.1.2 用 Microsoft Edge 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="eafdc-184">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.2</span></span>  

<span data-ttu-id="eafdc-185">[Visual Studio Code 用 Microsoft Edge 開発者ツール][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]拡張バージョン 1.1.2。前回リリース以降に Microsoft Visual Studio コードで次の変更がありました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-185">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.2 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="eafdc-186">Microsoft Visual Studio Code では拡張機能を自動的に更新しています。</span><span class="sxs-lookup"><span data-stu-id="eafdc-186">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="eafdc-187">バージョン 1.1.2 に手動で更新するには、[拡張機能を手動で更新][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-187">To manually update to version 1.1.2, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  

*   <span data-ttu-id="eafdc-188">ターゲット リストの各アイテムに **インスタンスを閉じる** ボタンを追加しました \([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248]\)</span><span class="sxs-lookup"><span data-stu-id="eafdc-188">Added a **Close instance** button to each item on the target list \([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248]\)</span></span>  
*   <span data-ttu-id="eafdc-189">84.0.522.63 から [85.0.564.40][DevtoolsWhatsNew85] に[Microsoft Edge DevTools][DevtoolsMain] バージョンを更新しました \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\)</span><span class="sxs-lookup"><span data-stu-id="eafdc-189">Bumped [Microsoft Edge DevTools][DevtoolsMain] version from 84.0.522.63 to [85.0.564.40][DevtoolsWhatsNew85] \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\)</span></span>  
*   <span data-ttu-id="eafdc-190">依存関係として [Microsoft Edge 用デバッガー][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] が含まれました  \([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233]\)</span><span class="sxs-lookup"><span data-stu-id="eafdc-190">Included [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] as a dependency  \([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233]\)</span></span>  
*   <span data-ttu-id="eafdc-191">設定オプションを実装して、拡張テーマを変更しました \([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229]\)</span><span class="sxs-lookup"><span data-stu-id="eafdc-191">Implemented settings option to change extension themes \([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229]\)</span></span>  
    
<span data-ttu-id="eafdc-192">[vscode-edge-devtools GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]で問題をファイルすると、拡張機能に貢献できます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-192">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="eafdc-193">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="eafdc-193">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="capture-node-screenshot-beyond-viewport"></a><span data-ttu-id="eafdc-194">ビューポート以外のノードのスクリーンショットをキャプチャ</span><span class="sxs-lookup"><span data-stu-id="eafdc-194">Capture node screenshot beyond viewport</span></span>  

<span data-ttu-id="eafdc-195">Microsoft Edge バージョン 89 では、ノードのスクリーンショットはもっと精度が高く、ノードのコンテンツがビューポートに表示されない場合でも、ノード全体をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-195">In Microsoft Edge version 89, node screenshots are more accurate, capturing the full node even if content from the node is not visible in the viewport.</span></span>  <span data-ttu-id="eafdc-196">**要素** ツールで、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、**ノードのスクリーンショットをキャプチャ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-196">In the **Elements** tool, hover  on an element, open the contextual menu \(right-click\), and choose **Capture node screenshot**.</span></span>  <span data-ttu-id="eafdc-197">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1003629][CR1003629] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-197">To review the history of this feature in the Chromium open-source project, navigate to Issue [1003629][CR1003629].</span></span>  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="[ノードのスクリーンショットをキャプチャ] を要素ツールのコンテキスト メニューで強調表示しました" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   <span data-ttu-id="eafdc-199">**ノードのスクリーンショットをキャプチ** を **要素** ツールのコンテキスト メニューで強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-199">**Capture node screenshot** highlighted on the context menu in the **Elements** tool</span></span>  
:::image-end:::  

### <a name="elements-tool-updates"></a><span data-ttu-id="eafdc-200">要素ツールの更新</span><span class="sxs-lookup"><span data-stu-id="eafdc-200">Elements tool updates</span></span>  

#### <a name="support-forcing-the-target-css-state"></a><span data-ttu-id="eafdc-201">:target CSS 強制をサポート</span><span class="sxs-lookup"><span data-stu-id="eafdc-201">Support forcing the :target CSS state</span></span>  

<span data-ttu-id="eafdc-202">DevTools を使用して、[:target][MdnDocsWebCssTarget] CSS 擬似クラスを強制的に適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-202">You may now use DevTools to force the [:target][MdnDocsWebCssTarget] CSS pseudo-class.</span></span>  <span data-ttu-id="eafdc-203">`:target` 擬似クラスは、一意の要素 \(the target element\) に URL のフラグメントと一致する `id` がある場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-203">The `:target` pseudo-class is triggered when a unique element \(the target element\) has an `id` that matches a fragment of the URL.</span></span>  <span data-ttu-id="eafdc-204">たとえば、`http://www.example.com/index.html#section1` URL は `id="section1"` を使用して HTML 要素の `:target` 擬似クラスをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-204">For example, the `http://www.example.com/index.html#section1` URL triggers the `:target` pseudo-class on an HTML element with `id="section1"`.</span></span>  <span data-ttu-id="eafdc-205">セクション 1 が強調表示されたデモを試す場合は、[CSS :target デモ][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-205">To try a demo with section 1 highlighted, navigate to [CSS :target demo][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1].</span></span>  <span data-ttu-id="eafdc-206">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1156628][CR1156628] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-206">To review the history of this feature in the Chromium open-source project, navigate to Issue [1156628][CR1156628].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="Web ページを強制的に CSS を適用しないで強調表示しました" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         <span data-ttu-id="eafdc-208">Web ページを強制的に CSS を適用しないで強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-208">Webpage highlighted with no forced CSS</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text=":target CSS を強制的に適用し、Web ページを強調表示しました" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` <span data-ttu-id="eafdc-210">CSS を強制的に適用し、Web ページを強調表示しました</span><span class="sxs-lookup"><span data-stu-id="eafdc-210">CSS forced and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <a name="use-duplicate-elements-to-copy-elements"></a><span data-ttu-id="eafdc-211">[要素を複製] を使用して要素をコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-211">Use Duplicate elements to copy elements</span></span>  

<span data-ttu-id="eafdc-212">新しい **要素を複製** ショートカットを使用して要素をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-212">Use the new **Duplicate element** shortcut to clone an element.</span></span>  <span data-ttu-id="eafdc-213">**要素** ツールで、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、**要素を複製**を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-213">In the **Elements** tool, hover on an element, open the contextual menu \(right-click\), choose **Duplicate element**.</span></span>  <span data-ttu-id="eafdc-214">選択した要素の下に新しい要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-214">A new element is created under the selected element.</span></span>  <span data-ttu-id="eafdc-215">キーボード ショートカットを使用して要素を複製するには、`Shift`+`Alt`+`Down Arrow` \(Windows/Linux\) または `Shift`+`Option`+`Down Arrow` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-215">To duplicate the element with a keyboard shortcut, select `Shift`+`Alt`+`Down Arrow` \(Windows/Linux\) or `Shift`+`Option`+`Down Arrow` \(macOS\).</span></span>  <span data-ttu-id="eafdc-216">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1150797][CR1150797] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-216">To review the history of this feature in the Chromium open-source project, navigate to Issue [1150797][CR1150797].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="[要素を複製] が [要素] ツールの要素の上にあるコンテキスト メニューで強調表示されます" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   <span data-ttu-id="eafdc-218">**要素を複製** が **要素** ツールの要素の上にあるコンテキスト メニューで強調表示されます</span><span class="sxs-lookup"><span data-stu-id="eafdc-218">The **Duplicate element** is highlighted in the context menu on an element in the **Elements** tool</span></span>  
:::image-end:::  

#### <a name="color-pickers-for-custom-css-properties"></a><span data-ttu-id="eafdc-219">カスタム CSS プロパティのカラー ピッカー</span><span class="sxs-lookup"><span data-stu-id="eafdc-219">Color pickers for custom CSS properties</span></span>  

<span data-ttu-id="eafdc-220">**スタイル** ウィンドウ に、カスタム CSS プロパティのカラー ピッカーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-220">The **Styles** pane now displays color pickers for custom CSS properties.</span></span>  <span data-ttu-id="eafdc-221">色の値の RGBA、HSLA、および Hex 形式を循環させるには、`Shift` を長押ししてカラー ピッカー選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-221">To cycle through the RGBA, HSLA, and Hex formats of the color value, hold `Shift` and choose the color picker.</span></span>  <span data-ttu-id="eafdc-222">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1147016][CR1147016] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-222">To review the history of this feature in the Chromium open-source project, navigate to Issue [1147016][CR1147016].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="カスタム CSS プロパティのカラー ピッカー" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   <span data-ttu-id="eafdc-224">カスタム CSS プロパティのカラー ピッカー</span><span class="sxs-lookup"><span data-stu-id="eafdc-224">Color pickers for custom CSS properties</span></span>  
:::image-end:::  

#### <a name="copy-css-classes-and-properties"></a><span data-ttu-id="eafdc-225">CSS クラスとプロパティをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-225">Copy CSS classes and properties</span></span>  

<span data-ttu-id="eafdc-226">コンテキスト メニューでいくつかの新しいオプションを使用して、CSS プロパティを簡単にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-226">You may now copy CSS properties quicker with a few new options in the contextual menu.</span></span>  <span data-ttu-id="eafdc-227">**要素** ツールで、任意の要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-227">In the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="eafdc-228">値をコピーするには、**スタイル** ウィンドウで CSS クラスまたは CSS プロパティにマウス ポインターを置いてから、コンテキスト メニュー \(右クリック\) を開き、コピー オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-228">To copy the value, in the **Styles** pane, hover on a CSS class or a CSS property, open a contextual menu \(right-click\), and choose the copy option.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="eafdc-229">CSS クラスのオプションをコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-229">Copy options for a CSS class.</span></span>  
      
      | <span data-ttu-id="eafdc-230">オプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-230">Option</span></span> | <span data-ttu-id="eafdc-231">詳細</span><span class="sxs-lookup"><span data-stu-id="eafdc-231">Details</span></span> |  
      |:--- |:--- |  
      | **<span data-ttu-id="eafdc-232">セレクターをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-232">Copy selector</span></span>** | <span data-ttu-id="eafdc-233">現在のセレクター名をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-233">Copy the current selector name.</span></span> |  
      | **<span data-ttu-id="eafdc-234">ルールをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-234">Copy rule</span></span>** | <span data-ttu-id="eafdc-235">現在のセレクターのルールをコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-235">Copy the rule of the current selector.</span></span> |  
      | **<span data-ttu-id="eafdc-236">すべての宣言をコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-236">Copy all declarations</span></span>** | <span data-ttu-id="eafdc-237">現在のルールで無効なプロパティとプレフィックス付きプロパティを含むすべての宣言をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-237">Copy all declarations under the current rule, including non-valid and prefixed properties.</span></span> |  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="eafdc-238">CSS プロパティのオプションをコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-238">Copy options for a CSS property.</span></span>  
      
      | <span data-ttu-id="eafdc-239">オプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-239">Option</span></span> | <span data-ttu-id="eafdc-240">詳細</span><span class="sxs-lookup"><span data-stu-id="eafdc-240">Details</span></span> |      
      |:--- |:--- |  
      | **<span data-ttu-id="eafdc-241">宣言をコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-241">Copy declaration</span></span>** | <span data-ttu-id="eafdc-242">現在の行の宣言をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-242">Copy the declaration of the current line.</span></span> |  
      | **<span data-ttu-id="eafdc-243">プロパティをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-243">Copy property</span></span>** | <span data-ttu-id="eafdc-244">現在の行のプロパティをコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-244">Copy the property of the current line.</span></span> |  
      | **<span data-ttu-id="eafdc-245">値をコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-245">Copy value</span></span>** | <span data-ttu-id="eafdc-246">現在の行の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-246">Copy the value of the current line.</span></span> |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="コンテキスト メニューで CSS クラスのオプションをコピー" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         <span data-ttu-id="eafdc-248">コンテキスト メニューで CSS クラスのオプションをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-248">Copy options for a CSS class in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="コンテキスト メニューの CSS プロパティのオプションをコピー" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         <span data-ttu-id="eafdc-250">コンテキスト メニューの CSS プロパティのオプションをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-250">Copy options for a CSS property in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="eafdc-251">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1152391][CR1152391] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-251">To review the history of this feature in the Chromium open-source project, navigate to Issue [1152391][CR1152391].</span></span>  

### <a name="cookies-updates"></a><span data-ttu-id="eafdc-252">Cookie の更新</span><span class="sxs-lookup"><span data-stu-id="eafdc-252">Cookies updates</span></span>  

#### <a name="new-option-to-display-url-decoded-cookies"></a><span data-ttu-id="eafdc-253">URL デコードされた Cookie を表示する新しいオプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-253">New option to display URL-decoded cookies</span></span>  

<span data-ttu-id="eafdc-254">これで、**Cookie** ウィンドウで URL デコードされた Cookie の値を表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-254">You may now opt to display the URL-decoded cookies value in the **Cookies** pane.</span></span>  <span data-ttu-id="eafdc-255">デコードされた Cookie を表示するには、**アプリケーション** > **Cookie** ウィンドウの順に移動し、リストで任意の Cookie を選択してから**URL デコードを表示** の横にあるチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-255">To display the decoded cookie, navigate to **Application** > **Cookies** pane, choose any cookie on the list, and choose the checkbox next to **Show URL decoded**.</span></span>  <span data-ttu-id="eafdc-256">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [997625][CR997625] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-256">To review the history of this feature in the Chromium open-source project, navigate to Issue [997625][CR997625].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="URL デコードされた Cookie を表示するオプション" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   <span data-ttu-id="eafdc-258">URL デコードされた Cookie を表示するオプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-258">Option to display URL decoded cookies</span></span>  
:::image-end:::  

#### <a name="filter-and-clear-visible-cookies"></a><span data-ttu-id="eafdc-259">表示される Cookie をフィルター処理してクリア</span><span class="sxs-lookup"><span data-stu-id="eafdc-259">Filter and clear visible cookies</span></span>  

<span data-ttu-id="eafdc-260">Microsoft Edge バージョン 88 以前では、**アプリケーション** ツールでは **すべての Cookie をクリア** ボタンを使用して、すべての Cookie をクリアする方法のみを提供しました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-260">In Microsoft Edge version 88 or earlier, the **Application** tool only provided a way to clear all cookies with the **Clear all cookies** button.</span></span>  <span data-ttu-id="eafdc-261">Microsoft Edge バージョン 89 では、**フィルター処理された Cookie をクリア** を選択して、フィルター処理された Cookie のみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-261">In Microsoft Edge version 89, you may now choose **Clear filtered cookies** to delete only the filtered cookies.</span></span>  <span data-ttu-id="eafdc-262">Cookie をフィルター処理するには、**アプリケーション** > **Cookie** の順に移動し、**フィルター処理** テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-262">To filter cookies, navigate to **Application** > **Cookies**, and type in the **Filter** textbox.</span></span>  <span data-ttu-id="eafdc-263">表示された Cookie を削除するには、**フィルター処理された Cookie をクリア** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-263">To delete the displayed cookies, choose the **Clear filtered cookies** button.</span></span>  <span data-ttu-id="eafdc-264">他のすべての Cookie を表示するには、フィルター テキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-264">To display all other cookies, clear the filter text.</span></span>  <span data-ttu-id="eafdc-265">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [978059][CR978059] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-265">To review the history of this feature in the Chromium open-source project, navigate to Issue [978059][CR978059].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="表示されている Cookie のみをクリア" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   <span data-ttu-id="eafdc-267">表示されている Cookie のみをクリア</span><span class="sxs-lookup"><span data-stu-id="eafdc-267">Clear only visible cookies</span></span>  
:::image-end:::  

#### <a name="new-option-to-clear-third-party-cookies-in-the-storage-pane"></a><span data-ttu-id="eafdc-268">ストレージ ウィンドウでサードパーティの Cookie をクリアする新しいオプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-268">New option to clear third-party cookies in the Storage pane</span></span>  

<span data-ttu-id="eafdc-269">DevTools では、既定でファースト パーティの Cookie のみをクリアします。</span><span class="sxs-lookup"><span data-stu-id="eafdc-269">DevTools now clear only first-party cookies by default.</span></span>  <span data-ttu-id="eafdc-270">Web サイトのデータとファースト パーティの Cookie のみをクリアするには、**アプリケーション** > **ストレージ** の順に移動してから、**サイト データをクリア** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-270">To clear website data and first-party cookies only, navigate to **Application** > **Storage**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="eafdc-271">Web サイトのデータとすべての Cookie をクリアするには、**アプリケーション** > **ストレージ** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-271">To clear website data and all cookies, navigate to **Application** > **Storage**.</span></span>  <span data-ttu-id="eafdc-272">**サードパーティの Cookie を含む** の横にあるチェック ボックスを選択して、**サイトのデータをクリア** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-272">Choose the checkbox next to **including third-party cookies**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="eafdc-273">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1012337][CR1012337] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-273">To review the history of this feature in the Chromium open-source project, navigate to Issue [1012337][CR1012337].</span></span>  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="サードパーティの Cookie をクリアするオプション" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   <span data-ttu-id="eafdc-275">サードパーティの Cookie をクリアするオプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-275">Option to clear third-party cookies</span></span>  
:::image-end:::  

### <a name="network-tool-updates"></a><span data-ttu-id="eafdc-276">ネットワーク ツールの更新</span><span class="sxs-lookup"><span data-stu-id="eafdc-276">Network tool updates</span></span>  

#### <a name="persist-record-network-log-setting"></a><span data-ttu-id="eafdc-277">ネットワーク ログの永続記録設定</span><span class="sxs-lookup"><span data-stu-id="eafdc-277">Persist Record network log setting</span></span>  

<span data-ttu-id="eafdc-278">Microsoft Edge バージョン 88 以前では、Web ページの更新時に DevTools で **ネットワーク ログを記録** の設定がリセットされていました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-278">In Microsoft Edge version 88 or earlier, DevTools reset the **Record network log** setting when a webpage refreshes.</span></span>  <span data-ttu-id="eafdc-279">Microsoft Edge バージョン 89 では、**ネットワーク ログを記録** の設定が保存されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-279">In Microsoft Edge version 89, DevTools now persist the **Record network log** setting.</span></span>  <span data-ttu-id="eafdc-280">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1122580][CR1122580] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-280">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122580][CR1122580].</span></span>  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="ネットワーク ログを記録" lightbox="../../media/2021/01/network-log.msft.png":::
   <span data-ttu-id="eafdc-282">ネットワーク ログを記録</span><span class="sxs-lookup"><span data-stu-id="eafdc-282">Record network log</span></span>  
:::image-end:::  

#### <a name="online-option-is-now-no-throttling-option"></a><span data-ttu-id="eafdc-283">オンライン オプションが調整なしのオプションになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-283">Online option is now No throttling option</span></span>  

<span data-ttu-id="eafdc-284">ネットワーク エミュレーション オプション **オンライン** が **調整なし** に変更されました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-284">The network emulation option **Online** is now renamed to **No Throttling**.</span></span>  <span data-ttu-id="eafdc-285">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1028078][CR1028078] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-285">To review the history of this feature in the Chromium open-source project, navigate to Issue [1028078][CR1028078].</span></span>  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="調整オプションなし" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   <span data-ttu-id="eafdc-287">**調整なし** オプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-287">**No throttling** option</span></span>  
:::image-end:::  

### <a name="new-copy-options-in-the-console-tool-sources-tool-and-styles-pane"></a><span data-ttu-id="eafdc-288">[コンソール] ツール、[ソース] ツール、[スタイル] ウィンドウの新しいコピー オプション</span><span class="sxs-lookup"><span data-stu-id="eafdc-288">New copy options in the Console tool, Sources tool, and Styles pane</span></span>

#### <a name="copy-object-in-the-console-and-sources-tool"></a><span data-ttu-id="eafdc-289">[コンソール] ツール、[ソース] ツールのオブジェクトをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-289">Copy object in the Console and Sources tool</span></span>  

<span data-ttu-id="eafdc-290">**[コンソール]** ツールと **[ソース]** ツールでオブジェクトの値をコピーできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-290">You may now copy object values in the **Console** and **Sources** tools.</span></span>  <span data-ttu-id="eafdc-291">オブジェクトの値をコピーする機能は、大きなオブジェクトを操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="eafdc-291">The ability to copy object values is useful when working with large objects.</span></span>  <span data-ttu-id="eafdc-292">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1148353][CR1148353] と問題 [1149859][CR1149859] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-292">To review the history of this feature in the Chromium open-source project, navigate to Issues [1148353][CR1148353] and [1149859][CR1149859].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="eafdc-293">**コンソール** ツール で、オブジェクトにマウス ポインターを置いてから、コンテキスト メニュー \(右クリック\) を開いてから **オブジェクトをコピー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-293">In the **Console** tool, hover on an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="eafdc-294">**ソース** ツールのブレークポイントで、オブジェクトにマウス ポインターを置き、**オブジェクト** ポップアップ ウィンドウでオブジェクトを強調表示してから、コンテキスト メニュー \(右クリック\) を開いて **オブジェクトをコピー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-294">In the **Sources** tool, on a breakpoint, hover on an object, in the **Object** popup window, highlight an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="コンソールでオブジェクトをコピー" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         <span data-ttu-id="eafdc-296">**コンソール** でオブジェクトをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-296">Copy object in the **Console**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="ソースでオブジェクトをコピー" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         <span data-ttu-id="eafdc-298">**ソース** でオブジェクトをコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-298">Copy object in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="copy-file-name-in-the-sources-tool-and-styles-pane"></a><span data-ttu-id="eafdc-299">[ソース] ツールと [スタイル] ウィンドウでファイル名をコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-299">Copy file name in the Sources tool and Styles pane</span></span>  

<span data-ttu-id="eafdc-300">これで、コンテキスト メニューを使用してファイル名をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-300">You may now copy a file name using the contextual menu.</span></span>  <span data-ttu-id="eafdc-301">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1155120][CR1155120] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-301">To review the history of this feature in the Chromium open-source project, navigate to Issues [1155120][CR1155120].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="eafdc-302">**ソース** ツールで、ファイル名にマウス ポインターを置いて、コンテキスト メニュー \(右クリック\) を開いてから **ファイル名をコピー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-302">In the **Sources** tool, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="eafdc-303">**要素** ツール > **スタイル** ウィンドウの順に移動して、ファイル名にマウス ポインターを置いてから、コンテキスト メニュー \(右クリック\) を開いて **ファイル名をコピー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-303">In the **Elements** tool > **Styles** pane, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="[ソース] でファイル名をコピー" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         <span data-ttu-id="eafdc-305">**ソース** でファイル名をコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-305">Copy file name in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="[スタイル] ウィンドウでファイル名をコピー" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         <span data-ttu-id="eafdc-307">**スタイル** ウィンドウでファイル名をコピー</span><span class="sxs-lookup"><span data-stu-id="eafdc-307">Copy file name in **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="updates-to-frame-details"></a><span data-ttu-id="eafdc-308">フレームの詳細の更新</span><span class="sxs-lookup"><span data-stu-id="eafdc-308">Updates to Frame details</span></span>  

#### <a name="service-workers-information-in-frame-details"></a><span data-ttu-id="eafdc-309">フレームの詳細のサービス ワーカー情報</span><span class="sxs-lookup"><span data-stu-id="eafdc-309">Service Workers information in Frame details</span></span>  

<span data-ttu-id="eafdc-310">DevTools では、親フレームで専用のサービス ワーカーが一覧表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eafdc-310">DevTools now lists a dedicated service worker under the parent frame.</span></span>  <span data-ttu-id="eafdc-311">次の図では、サービス ワーカーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-311">In the following figure, service worker details are displayed.</span></span>  <span data-ttu-id="eafdc-312">サービス ワーカーの詳細を表示するには、**アプリケーション** > **フレーム** > `top` > **サービス ワーカー**の順に移動して、サービス ワーカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-312">To display the service worker details, navigate to **Application** > **Frames** > `top` > **Service Workers** and then choose a service worker.</span></span>  <span data-ttu-id="eafdc-313">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1122507][CR1122507] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-313">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122507][CR1122507].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="フレームの詳細のサービス ワーカー情報" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   <span data-ttu-id="eafdc-315">**フレーム** の詳細の **サービス ワーカー** 情報</span><span class="sxs-lookup"><span data-stu-id="eafdc-315">**Service Workers** information in the **Frames** details</span></span>  
:::image-end:::  

#### <a name="measure-memory-information-in-frame-details"></a><span data-ttu-id="eafdc-316">フレームの詳細でメモリ情報を測定</span><span class="sxs-lookup"><span data-stu-id="eafdc-316">Measure Memory information in Frame details</span></span>  

<span data-ttu-id="eafdc-317">`performance.measureMemory()`API 状態が、**API 可用性** セクションの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-317">The `performance.measureMemory()` API status is now displayed under the **API availability** section.</span></span>  <span data-ttu-id="eafdc-318">新しい `performance.measureMemory()` API は、Web ページ全体のメモリ使用量を推定します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-318">The new `performance.measureMemory()` API estimates the memory usage of the entire webpage.</span></span>  <span data-ttu-id="eafdc-319">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1139899][CR1139899] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-319">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="メモリを測定" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   <span data-ttu-id="eafdc-321">メモリを測定</span><span class="sxs-lookup"><span data-stu-id="eafdc-321">Measure Memory</span></span>  
:::image-end:::  

### <a name="dropped-frames-in-the-performance-tool"></a><span data-ttu-id="eafdc-322">パフォーマンス ツールでのフレームをドロップしました</span><span class="sxs-lookup"><span data-stu-id="eafdc-322">Dropped frames in the Performance tool</span></span>  

<span data-ttu-id="eafdc-323">[パフォーマンス ツールで読み込みパフォーマンスを分析][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance] する場合、**フレーム** セクションではドロップされたフレームが赤でマークされます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-323">When you [analyze load performance in the Performance tool][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance], the **Frames** section now marks dropped frames as red.</span></span>  <span data-ttu-id="eafdc-324">フレーム レートを表示するには、ドロップしたフレームにマウス ポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-324">To display the frame rate, hover on a dropped frame.</span></span>  <span data-ttu-id="eafdc-325">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1075865][CR1075865] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-325">To review the history of this feature in the Chromium open-source project, navigate to Issue [1075865][CR1075865].</span></span>  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="フレームをドロップしました" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   <span data-ttu-id="eafdc-327">フレームをドロップしました</span><span class="sxs-lookup"><span data-stu-id="eafdc-327">Dropped frames</span></span>  
:::image-end:::  

#### <a name="new-color-contrast-calculation---advanced-perceptual-contrast-algorithm-apca"></a><span data-ttu-id="eafdc-328">新しいカラー コントラスト計算 - 高度な知覚コントラスト アルゴリズム (APCA)</span><span class="sxs-lookup"><span data-stu-id="eafdc-328">New color contrast calculation - Advanced Perceptual Contrast Algorithm (APCA)</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="eafdc-329">[高度な知覚コントラスト アルゴリズム (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] は、[カラー ピッカー][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker] の [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] ガイドラインのコントラスト比を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-329">The [Advanced Perceptual Contrast Algorithm (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] replaces the [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] guidelines contrast ratio in the [Color Picker][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker].</span></span>  <span data-ttu-id="eafdc-330">APCA は、コントラストを計算する新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="eafdc-330">APCA is a new way to compute contrast.</span></span>  <span data-ttu-id="eafdc-331">これは、色覚に関する最新の研究に基づいています。</span><span class="sxs-lookup"><span data-stu-id="eafdc-331">It is based on modern research on color perception.</span></span>  <span data-ttu-id="eafdc-332">AA/AAA ガイドラインと比較すると、APCA はコンテキストに依存します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-332">Compared to AA/AAA guidelines, APCA is more context-dependent.</span></span>  <span data-ttu-id="eafdc-333">コントラストは、テキスト、色、コンテキストの次の空間プロパティに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-333">The contrast is calculated based on the following spatial properties of the text, color, and context.</span></span>  

*   <span data-ttu-id="eafdc-334">フォントの太さとサイズが含まれるテキストの空間プロパティ。</span><span class="sxs-lookup"><span data-stu-id="eafdc-334">Spatial properties of text that include font weight and size.</span></span>  
*   <span data-ttu-id="eafdc-335">テキストと背景間で認識されているコントラストが含まれる色彩空間プロパティ。</span><span class="sxs-lookup"><span data-stu-id="eafdc-335">Spatial properties of color that include perceived contrast between text and background.</span></span>  
*   <span data-ttu-id="eafdc-336">環境光、周囲、および目的の意図が含まれるコンテキスト空間プロパティ。</span><span class="sxs-lookup"><span data-stu-id="eafdc-336">Spatial properties of context that include ambient light, surroundings, and intended purpose.</span></span>  
    
<span data-ttu-id="eafdc-337">この実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**以前のコントラスト比と AA/AAA ガイドラインを置き換える高度な知覚コントラスト アルゴリズム (APCA) を有効にする** の横にあるチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-337">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable new Advanced Perceptual Contrast Algorithm (APCA) replacing previous contrast ratio and AA/AAA guidelines**.</span></span>  <span data-ttu-id="eafdc-338">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1121900][CR1121900] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafdc-338">To review the history of this feature in the Chromium open-source project, navigate to Issue [1121900][CR1121900].</span></span>  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="カラー ピッカーの APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   <span data-ttu-id="eafdc-340">カラー ピッカーの APCA</span><span class="sxs-lookup"><span data-stu-id="eafdc-340">APCA in the Color Picker</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="eafdc-341">Microsoft Edge プレビュー チャネルをダウンロード</span><span class="sxs-lookup"><span data-stu-id="eafdc-341">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="eafdc-342">Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="eafdc-342">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="eafdc-343">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eafdc-343">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="eafdc-344">Microsoft Edge DevTools チームに連絡</span><span class="sxs-lookup"><span data-stu-id="eafdc-344">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "DevTools (Microsoft Edge 85) の新機能 | Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "カラー ピッカー - アクセシビリティ リファレンス ページでテキスト要素のコントラスト比を表示 | Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "CSS の変更 - CSS 参照|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "折りたたみ可能なデバイスとデュアルスクリーン デバイスでのテスト - Microsoft Edge DevTools でデュアルスクリーン デバイスと折りたたみ可能なデバイスをエミュレート | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートのシミュレート - Microsoft Edge DevTools でモバイル デバイスをエミュレート | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "レコードの読み込みパフォーマンス - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集 | Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 開発者ツールの概要 |Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "セクション 1 - DevTools 新機能への CSS :target デモ(Microsoft Edge 89) |GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "プル 229: 設定でドロップダウンを実装して、テーマを変更 | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "プル 233: 依存関係として Microsoft Edge 用デバッガーを含む | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "プル 235: Microsoft Edge DevTools バージョンを 85.0.564.40 にアップグレード | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "プル 248: インスタンス パネルに 1 つの[閉じる]ボタンを追加 | GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "フォントの特性と背景色を選択して、読みやすいコントラストを設定 | W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "信頼できる型 | W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface Duo | Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Visual Studio Code 用 Microsoft Edge Tools |Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  
[CR978059]: https://crbug.com/978059 "問題 978059: フィルター処理時に Cookie を削除する場合、フィルター処理されたものだけでなくすべての Cookie が削除される | Chromium のバグ"  
[CR997625]: https://crbug.com/997625 "問題 997625: 新機能要求 | Cookie で URL デコードされた値を表示するオプションが必要 | Chromium のバグ"  
[CR1003629]: https://crbug.com/1003629 "問題 1003629: ノードをキャプチャする機能でフォールドの下のノードをスクリーンショットできない。 | Chromium のバグ"  
[CR1012337]: https://crbug.com/1012337 "問題 1012337: サイトのデータを消去すると、Google 以外のサイトで Google セッションが破棄される | Chromium のバグ"  
[CR1028078]: https://crbug.com/1028078 "問題 1028078: リストで [オンライン] と [オフライン] が並んで表示される | Chromium のバグ"  
[CR1054281]: https://crbug.com/1054281 "問題 1054281: 機能要求: DevTools で、折りたたみ可能デバイスとデュアルスクリーン デバイスをエミュレートする必要がある | Chromium のバグ"  
[CR1075865]: https://crbug.com/1075865 "問題 1075865: DevTools タイムラインにドロップ済みのフレームが表示される | Chromium のバグ"  
[CR1093229]: https://crbug.com/1093229 "問題 1093229: DevTools: 特殊な書体エディター UI を提供 | Chromium のバグ"  
[CR1121900]: https://crbug.com/1121900 "問題 1121900: DevTools: 新しい仕様ごとにコントラスト計算ロジックを更新 | Chromium のバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレーム ツリー ビューでの Surface ワーカー情報 | Chromium のバグ"  
[CR1122580]: https://crbug.com/1122580 "問題 1122580: 再読み込み時にネットワーク記録を無効にできない | Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox ツール | Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレーム詳細ビューでゲート API の可用性を報告する | Chromium のバグ"  
[CR1139949]: https://crbug.com/1139949 "問題 1139949: Flexbox オーバーレイ | Chromium のバグ"  
[CR1147016]: https://crbug.com/1147016 "問題 1147016: カラー ピッカーが var() 関数に表示されない。 | Chromium のバグ"  
[CR1148353]: https://crbug.com/1148353 "問題 1148353: 機能要求: DevTools コンソール からオブジェクトをコピー | Chromium のバグ"  
[CR1149859]: https://crbug.com/1149859 "Issue 1149859: [機能要求][コンソール] のコンテキスト メニューに [オブジェクトをクリップボード アイテムにコピー] を追加 | Chromium のバグ"  
[CR1150797]: https://crbug.com/1150797 "問題 1150797: [要素] パネルに要素コンテキスト メニューの複製を追加 | Chromium のバグ"  
[CR1152391]: https://crbug.com/1152391 "問題 1152391: スタイル パネルの CSS コンテキスト メニューのコピーへのサポート | Chromium のバグ"  
[CR1155120]: https://crbug.com/1155120 "問題 1155120: [FR]サポートのコピー ファイル名と行番号 | Chromium のバグ"  
[CR1156628]: https://crbug.com/1156628 "問題 1156628: DevTools: :target 強制要素の状態機能のサポートを追加 | Chromium のバグ"  
[CR1157329]: https://crbug.com/1157329 "問題 1157329: アクセシビリティ - ナレーター: ナレーターで、[スタイル] タブのコードに使用できる候補の数と位置がアナウンスされない | Chromium のバグ"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target ":target | MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "コントラスト (拡張) - WCAGを満たす方法 (クイック リファレンス) | W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "コントラスト (最小) - WCAG を満たす方法 (クイック リファレンス) | W3C"  

> [!NOTE]
> <span data-ttu-id="eafdc-399">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="eafdc-399">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="eafdc-400">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developer.chrome.com/blog/new-in-devtools-89)にあります。</span><span class="sxs-lookup"><span data-stu-id="eafdc-400">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-89) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="eafdc-402">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="eafdc-402">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "スパニング プレースホルダー"  
