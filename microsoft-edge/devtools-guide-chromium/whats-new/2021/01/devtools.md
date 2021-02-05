---
description: What's New ツールがウェルカム、スタイル ウィンドウの Visual Font Editor、CSS Flexbox デバッグ ツールなどです。
title: DevTools の新機能 (Microsoft Edge 89)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0a8a5e69281ced9421733059b554bd8cb997c7cd
ms.sourcegitcommit: 085046a5885c68243b763aaf6809fea43452403a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313777"
---
# <span data-ttu-id="e7809-104">DevTools の新機能 (Microsoft Edge 89)</span><span class="sxs-lookup"><span data-stu-id="e7809-104">What's New In DevTools (Microsoft Edge 89)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <span data-ttu-id="e7809-105">新機能へようこそ</span><span class="sxs-lookup"><span data-stu-id="e7809-105">What's New is now Welcome</span></span>  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="e7809-106">Microsoft \*\*\*\* Edge DevTools の新機能ツールに、新しい外観と新しい名前 "ようこそ" が追加**されています**。</span><span class="sxs-lookup"><span data-stu-id="e7809-106">The **What's New** tool in the Microsoft Edge DevTools now has a new appearance and a new name:  **Welcome**.</span></span>  <span data-ttu-id="e7809-107">ウェルカム **ツールには** 、最新の DevTools ニュースと更新プログラムが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-107">The **Welcome** tool still displays the latest DevTools news and updates.</span></span>  <span data-ttu-id="e7809-108">また、Microsoft Edge DevTools ドキュメントへのリンク、フィードバックの送信方法なども含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7809-108">It now also includes links to Microsoft Edge DevTools documentation, ways to submit feedback, and more.</span></span>  <span data-ttu-id="e7809-109">Microsoft Edge への更新 **の後** にウェルカム ツールを表示するには、タイトルの更新ごとに [開く] タブの横 **にある** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e7809-109">To display the **Welcome** tool after each update to Microsoft Edge, choose the checkbox next to **Open tab after each update** under the title.</span></span>  <span data-ttu-id="e7809-110">ウェルカム ツールを **閉** じるには、タブ タイトルの右側にある **[X]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-110">To close the **Welcome** tool, choose the **X** on the right-side of the tab title.</span></span>  <span data-ttu-id="e7809-111">元の新機能ツール**が**必要な場合は、[設定の実験[][DevtoolsCustomizeIndexSettings]] に移動し、[ようこそ] タブの横にある  >  \*\*\*\*\*\*チェック ボックスをオフにします\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7809-111">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="ウェルカム ツールが強調表示されている" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   <span data-ttu-id="e7809-113">ウェルカム **ツール** が強調表示されている</span><span class="sxs-lookup"><span data-stu-id="e7809-113">The **Welcome** tool is highlighted</span></span>  
:::image-end:::  

## <span data-ttu-id="e7809-114">[スタイル] ウィンドウの Visual Font Editor</span><span class="sxs-lookup"><span data-stu-id="e7809-114">Visual Font Editor in the Styles pane</span></span>  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="e7809-115">CSS でフォントを使用する場合は、新しいビジュアル フォント エディター [を使用します][DevtoolsInspectStylesEditFonts]。</span><span class="sxs-lookup"><span data-stu-id="e7809-115">When you work with fonts in CSS, use the new visual [Font Editor][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="e7809-116">フォールバック フォントを定義し、スライダーを使ってフォントの太さ、サイズ、行の高さ、間隔を定義できます。</span><span class="sxs-lookup"><span data-stu-id="e7809-116">You may define fallback fonts, and use sliders to define font weight, size, line-height, and spacing.</span></span>  <span data-ttu-id="e7809-117">フォント **エディターを使用すると** 、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7809-117">The **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="e7809-118">さまざまなフォント プロパティの単位を切り替える</span><span class="sxs-lookup"><span data-stu-id="e7809-118">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="e7809-119">さまざまなフォント プロパティのキーワードを切り替える</span><span class="sxs-lookup"><span data-stu-id="e7809-119">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="e7809-120">単位を変換する</span><span class="sxs-lookup"><span data-stu-id="e7809-120">Convert units</span></span>  
*   <span data-ttu-id="e7809-121">正確な CSS コードを生成する</span><span class="sxs-lookup"><span data-stu-id="e7809-121">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="e7809-122">この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、[スタイル] ウィンドウで新しいフォント エディター ツールを有効にするの横にある  >  \*\*\*\*\*\*チェック ボックスをオンにします\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7809-122">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new Font Editor tools within Styles pane**.</span></span>  <span data-ttu-id="e7809-123">詳細については、DevTools の [スタイル] ウィンドウの [CSS フォントのスタイルと設定 [の編集] に移動します][DevtoolsInspectStylesEditFonts]。</span><span class="sxs-lookup"><span data-stu-id="e7809-123">For more information, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="e7809-124">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1093229 に移動します][CR1093229]。</span><span class="sxs-lookup"><span data-stu-id="e7809-124">To review the history of this feature in the Chromium open-source project, navigate to Issue [1093229][CR1093229].</span></span>  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="[スタイル] ウィンドウで、視覚的なフォント エディターが強調表示されている" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   <span data-ttu-id="e7809-126">ビジュアル フォント **エディターが [** スタイル] ウィンドウ **で強調表示** されている</span><span class="sxs-lookup"><span data-stu-id="e7809-126">The visual **Font editor** is highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="e7809-127">CSS Flexbox デバッグ ツール</span><span class="sxs-lookup"><span data-stu-id="e7809-127">CSS Flexbox debugging tools</span></span>  

<span data-ttu-id="e7809-128">Flexbox のデバッグ機能は、アクティブな開発中です。</span><span class="sxs-lookup"><span data-stu-id="e7809-128">Flexbox debugging features are in active development.</span></span>  <span data-ttu-id="e7809-129">次の 2 つの機能の実験を有効にするには[][DevtoolsCustomizeIndexSettings]、[設定の実験] に移動し、[新しい CSS Flexbox デバッグ機能を有効にする] の横にあるチェック ボックス  >  \*\*\*\*\*\*をオンにします\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7809-129">To turn on the experiment for the following two features, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new CSS Flexbox debugging features**.</span></span>  <span data-ttu-id="e7809-130">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[問題 [1136394]][CR1136394] および [[1139949]][CR1139949]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-130">To review the history of this feature in the Chromium open-source project, navigate to Issues [1136394][CR1136394] and [1139949][CR1139949].</span></span>  

### <span data-ttu-id="e7809-131">新しい Flexbox (flex) アイコンは、flex コンテナーの識別と表示に役立ちます</span><span class="sxs-lookup"><span data-stu-id="e7809-131">New Flexbox (flex) icon helps identify and display flex containers</span></span>  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="e7809-132">Elements ツール **では** 、新しい Flexbox (flex) アイコンを使用して、コード内の Flexbox コンテナーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="e7809-132">In the **Elements** tool, the new Flexbox (flex) icon helps you identify Flexbox containers in your code.</span></span>  <span data-ttu-id="e7809-133">Flexbox \(flex\) アイコンを選択して、Flexbox コンテナーの輪郭を表示するオーバーレイ効果をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="e7809-133">Choose the Flexbox \(flex\) icon to turn on or off the overlay effect that outlines a Flexbox container.</span></span>  <span data-ttu-id="e7809-134">[レイアウト] ウィンドウの [スタイルと\*\*\*\* 計算] の横にあるオーバーレイの色**を\*\*\*\*カスタマイズできます**。</span><span class="sxs-lookup"><span data-stu-id="e7809-134">You may customize the color of the overlay in the **Layout** pane, which is located next to **Styles** and **Computed**.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e7809-135">Flexbox コンテナーの輪郭を引くオーバーレイ効果のオンとオフを切り替える場合は、Flexbox \( `flex` \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-135">To turn on and off the overlay effect that outlines the Flexbox container, choose the Flexbox \(`flex`\) icon.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e7809-136">[スタイルと計算] の横の [ **レイアウト** ] ウィンドウでオーバーレイの **色** を **カスタマイズできます**。</span><span class="sxs-lookup"><span data-stu-id="e7809-136">You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (flex) アイコンと Web ページが強調表示されている" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         <span data-ttu-id="e7809-138">**Flexbox** \( `flex` \) アイコンと Web ページが強調表示されている</span><span class="sxs-lookup"><span data-stu-id="e7809-138">The **Flexbox** \(`flex`\) icon and webpage highlighted</span></span> :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="レイアウト ウィンドウで強調表示されている Flexbox オーバーレイ" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         <span data-ttu-id="e7809-140">レイアウト**ウィンドウで強調表示**されている Flexbox**オーバーレイ**</span><span class="sxs-lookup"><span data-stu-id="e7809-140">The **Flexbox overlays** highlighted in the **Layout** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="e7809-141">CSS プロパティを使用して Flexbox レイアウトが変更された場合に配置アイコンとグリッド線を表示する</span><span class="sxs-lookup"><span data-stu-id="e7809-141">Display alignment icons and gridlines when Flexbox layouts change using CSS properties</span></span>  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="e7809-142">Flexbox レイアウトの CSS を編集すると、[スタイル] ウィンドウの\*\*\*\* CSS オートコンプリートに、関連する Flexbox プロパティの横に便利なアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-142">When you edit CSS for your Flexbox layout, CSS autocompletes in the **Styles** pane now displays helpful icons next to relevant Flexbox properties.</span></span>  <span data-ttu-id="e7809-143">この新機能を試す場合は **、Elements** ツールを開き、flex コンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-143">To try this new feature, open the **Elements** tool and select a flex container.</span></span>  <span data-ttu-id="e7809-144">次に、[スタイル] ウィンドウで、そのコンテナーのプロパティを **追加または変更** します。</span><span class="sxs-lookup"><span data-stu-id="e7809-144">Then add or change a property on that container in the **Styles** pane.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e7809-145">オートコンプリート メニューに、配置プロパティの効果を示すアイコンが表示 `align-content` されます `align-items` 。</span><span class="sxs-lookup"><span data-stu-id="e7809-145">The autocomplete menu now displays icons that indicate the effect of alignment properties such as `align-content` and `align-items`.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e7809-146">さらに、DevTools には CSS プロパティの確認に役立つガイド行が `align-items` 表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-146">Additionally, DevTools now displays a guiding line to help you better review the `align-items` CSS property.</span></span>  <span data-ttu-id="e7809-147">`gap`CSS プロパティもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e7809-147">The `gap` CSS property is supported as well.</span></span>  <span data-ttu-id="e7809-148">次の図では、CSS プロパティが設定され、ギャップごとにパターン `gap` `gap: 12px;` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-148">In the following figure, the `gap` CSS property is set to `gap: 12px;` and the hatching pattern for each gap is displayed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="配置で始まる CSS プロパティで強調表示されたオートコンプリート メニュー" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         <span data-ttu-id="e7809-150">次で始まる CSS プロパティで強調表示されたオートコンプリート メニュー</span><span class="sxs-lookup"><span data-stu-id="e7809-150">Autocomplete menu highlighted for CSS properties that start with</span></span> `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS プロパティと Web ページの Flexbox ギャップが強調表示されている" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         <span data-ttu-id="e7809-152">CSS プロパティ `gap` と Web ページの Flexbox が強調表示されている</span><span class="sxs-lookup"><span data-stu-id="e7809-152">Flexbox `gap` in CSS properties and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="e7809-153">新しい [その他のツール] ボタンを使用してツールをすばやく追加する</span><span class="sxs-lookup"><span data-stu-id="e7809-153">Add tools quickly with new More Tools button</span></span>  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="e7809-154">これで、Microsoft Edge DevTools でさらに多くのツールを開く新しい方法が追加されています。</span><span class="sxs-lookup"><span data-stu-id="e7809-154">You now have a new way to open more tools in the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="e7809-155">この実験を有効にした後、[\*\*\*\* その他のツール] アイコンは、メイン パネルの右側にプラス記号 ( `+` ) として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-155">After you turn on this experiment, the **More Tools** icon displays as a plus sign (`+`) to the right of the main panel.</span></span>  <span data-ttu-id="e7809-156">メイン パネルに追加する他のツールの一覧を表示するには、[\*\*\*\* その他のツール\ ( \) ] アイコン `+` を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-156">To display a list of other tools to add to the main panel, choose the **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="e7809-157">この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、[+ボタン タブメニューを有効にする] の横にあるチェック ボックスをオンにして、その他の  >  \*\*\*\*\*\*ツールを開きます\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7809-157">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**, and then choose the checkbox next to **Enable + button tab menus to open more tools**.</span></span>  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="DevTools で強調表示されているその他のツール" lightbox="../../media/2021/01/more-tools.msft.png":::
   <span data-ttu-id="e7809-159">**DevTools** で強調表示されているその他のツール</span><span class="sxs-lookup"><span data-stu-id="e7809-159">**More Tools** highlighted in DevTools</span></span>  
:::image-end:::  

## <span data-ttu-id="e7809-160">支援技術が CSS 候補の位置と数をアナウンスする</span><span class="sxs-lookup"><span data-stu-id="e7809-160">Assistive technologies now announce position and count of CSS suggestions</span></span>  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

<span data-ttu-id="e7809-161">CSS を編集すると、機能のドロップダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-161">When you edit CSS, you get a dropdown of features.</span></span>  <span data-ttu-id="e7809-162">この機能は、Microsoft Edge バージョン 89 で発表されたので、支援技術のユーザーは利用できません。</span><span class="sxs-lookup"><span data-stu-id="e7809-162">This feature was not available to users of assistive technologies, since it is announced in Microsoft Edge version 89.</span></span>  <span data-ttu-id="e7809-163">支援技術のユーザーが、[スタイル] ウィンドウで CSS 候補内を **移動する場合** があります。</span><span class="sxs-lookup"><span data-stu-id="e7809-163">A user of assistive technologies may now navigate CSS suggestions in the **Styles** pane.</span></span>  <span data-ttu-id="e7809-164">Microsoft Edge バージョン 88 以前では、ユーザーが [スタイル] ウィンドウで CSS を編集するときに提案の一覧を探して、支援技術が `Suggestion` **発表** されました。</span><span class="sxs-lookup"><span data-stu-id="e7809-164">In Microsoft Edge version 88 and earlier, assistive technology announced `Suggestion` as a user navigated through the list of suggestions when editing CSS in the **Styles** pane.</span></span>  <span data-ttu-id="e7809-165">Microsoft Edge バージョン 89 では、支援技術のユーザーに現在の提案の位置と数が聞こえる状態です。</span><span class="sxs-lookup"><span data-stu-id="e7809-165">In Microsoft Edge version 89, a user of assistive technology now hears the position and count of the current suggestion.</span></span>  <span data-ttu-id="e7809-166">各提案は、ユーザーが提案の一覧 (5 の提案 3 など) を移動すると発表されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-166">Each suggestion is announced as the user navigates through the list of suggestions, such as Suggestion 3 of 5.</span></span>  <span data-ttu-id="e7809-167">DevTools での CSS の記述の詳細については、「CSS の変更」に移動 [してください][DevtoolsCssReferenceChangeCss]。</span><span class="sxs-lookup"><span data-stu-id="e7809-167">To learn more about writing CSS in the DevTools, navigate to [Change CSS][DevtoolsCssReferenceChangeCss].</span></span>  <span data-ttu-id="e7809-168">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1157329 に移動します][CR1157329]。</span><span class="sxs-lookup"><span data-stu-id="e7809-168">To review the history of this feature in the Chromium open-source project, navigate to Issue [1157329][CR1157329].</span></span>  

<span data-ttu-id="e7809-169">この実験を有効にした状態で、いくつかの提案を表示して読み上げるビデオを表示するには、YouTube の [Devtools](https://youtu.be/9TcUpleEwwA) オプションを発表する Voiceover に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-169">To view a video that displays and reads aloud several suggestions with this experiment turned on, navigate to [Voiceover announcing devtools options](https://youtu.be/9TcUpleEwwA) on YouTube.</span></span>  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text="[スタイル] ウィンドウで強調表示されている候補" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   <span data-ttu-id="e7809-171">[ `suggestion` スタイル] ウィンドウで強調表示 **されている** 一覧</span><span class="sxs-lookup"><span data-stu-id="e7809-171">The `suggestion` list highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="e7809-172">Surface Duo と Samsung Galaxy Fold のエミュレート</span><span class="sxs-lookup"><span data-stu-id="e7809-172">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

<span data-ttu-id="e7809-173">Microsoft Edge の次のデバイスで、Web サイトまたはアプリの外観をテストします。</span><span class="sxs-lookup"><span data-stu-id="e7809-173">Test the appearance of your website or app on the following devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="e7809-174">Surface の一方</span><span class="sxs-lookup"><span data-stu-id="e7809-174">Surface Duo</span></span>][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [<span data-ttu-id="e7809-175">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="e7809-175">Samsung Galaxy Fold</span></span>][SamsungUsMobileGalaxyFold]  
    
<span data-ttu-id="e7809-176">試験的 **な Web プラットフォーム機能** を有効にし、新しい [CSS メディア][DualScreenWebCssMediaSpanning] 画面スパン機能にアクセスし [、getWindowSegments JavaScript API を取得します][DualScreenWebJavascriptGetwindowsegments]。</span><span class="sxs-lookup"><span data-stu-id="e7809-176">Turn on **Experimental Web Platform features** to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments].</span></span>  <span data-ttu-id="e7809-177">試験的 `edge://flags` な Web プラットフォーム機能の横にあるフラグ **に移動し、切り替える**。</span><span class="sxs-lookup"><span data-stu-id="e7809-177">Navigate to `edge://flags` and toggle the flag next to **Experimental Web Platform features**.</span></span>  <span data-ttu-id="e7809-178">デュアルスクリーン デバイスと折りたたみ式デバイスのために Web サイトやアプリを強化するには、[デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7809-178">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="e7809-179">[スパニング][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: Web サイト (またはアプリ) が両方の画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-179">[Spanning][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>  
*   <span data-ttu-id="e7809-180">[シームのレンダリング][DualScreenIntroductionHowToWorkWithSeam]: シームとは、2 つの画面の間の領域のことです。</span><span class="sxs-lookup"><span data-stu-id="e7809-180">[Rendering the seam][DualScreenIntroductionHowToWorkWithSeam], which is the space between the two screens.</span></span>  
    
<span data-ttu-id="e7809-181">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1054281 に移動します][CR1054281]。</span><span class="sxs-lookup"><span data-stu-id="e7809-181">To review the history of this feature in the Chromium open-source project, navigate to Issue [1054281][CR1054281].</span></span>  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="デュアルスクリーンをエミュレートする" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   <span data-ttu-id="e7809-183">デュアルスクリーンをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="e7809-183">Emulate dual-screen</span></span>  
:::image-end:::  

## <span data-ttu-id="e7809-184">Microsoft Edge Developer Tools for Visual Studio Code Version 1.1.2</span><span class="sxs-lookup"><span data-stu-id="e7809-184">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.2</span></span>  

<span data-ttu-id="e7809-185">[Microsoft Edge Developer Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.2 for Microsoft Visual Studio Code には、前のリリース以降に次の変更があります。</span><span class="sxs-lookup"><span data-stu-id="e7809-185">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.2 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="e7809-186">Microsoft Visual Studioコードは拡張機能を自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="e7809-186">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="e7809-187">バージョン 1.1.2 に手動で更新するには、[拡張機能を手動で [更新する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。</span><span class="sxs-lookup"><span data-stu-id="e7809-187">To manually update to version 1.1.2, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  

*   <span data-ttu-id="e7809-188">ターゲット リスト **\( #248** \) の各アイテムに [インスタンス[を閉じる] ボタンを][GithubMicrosoftVscodeEdgeDevtoolsPull248]追加しました</span><span class="sxs-lookup"><span data-stu-id="e7809-188">Added a **Close instance** button to each item on the target list \([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248]\)</span></span>  
*   <span data-ttu-id="e7809-189">84.0.522.63 から[85.0.564.40][DevtoolsWhatsNew85] \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\) [][DevtoolsMain]</span><span class="sxs-lookup"><span data-stu-id="e7809-189">Bumped [Microsoft Edge DevTools][DevtoolsMain] version from 84.0.522.63 to [85.0.564.40][DevtoolsWhatsNew85] \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\)</span></span>  
*   <span data-ttu-id="e7809-190">依存関係 [\(][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] #233 \) として Microsoft Edge[のデバッガーが含][GithubMicrosoftVscodeEdgeDevtoolsPull233]まれています</span><span class="sxs-lookup"><span data-stu-id="e7809-190">Included [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] as a dependency  \([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233]\)</span></span>  
*   <span data-ttu-id="e7809-191">拡張テーマ \( #229 \)[を変更する設定オプションを][GithubMicrosoftVscodeEdgeDevtoolsPull229]実装しました</span><span class="sxs-lookup"><span data-stu-id="e7809-191">Implemented settings option to change extension themes \([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229]\)</span></span>  
    
<span data-ttu-id="e7809-192">問題を解決し [、vscode-edge-devtools GitHub][GithubMicrosoftVscodeEdgeDevtools]リポジトリの拡張機能に投稿することができます。</span><span class="sxs-lookup"><span data-stu-id="e7809-192">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

## <span data-ttu-id="e7809-193">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="e7809-193">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="e7809-194">ビューポートを越えてノードのスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="e7809-194">Capture node screenshot beyond viewport</span></span>  

<span data-ttu-id="e7809-195">Microsoft Edge バージョン 89 では、ノードのスクリーンショットの方が正確で、ノードのコンテンツがビューポートに表示されない場合でも、ノード全体がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="e7809-195">In Microsoft Edge version 89, node screenshots are more accurate, capturing the full node even if content from the node is not visible in the viewport.</span></span>  <span data-ttu-id="e7809-196">要素ツール **で要素** をポイントし、コンテキスト メニュー \(右クリック\) を開き、[キャプチャ] ノードのスクリーンショット **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7809-196">In the **Elements** tool, hover  on an element, open the contextual menu \(right-click\), and choose **Capture node screenshot**.</span></span>  <span data-ttu-id="e7809-197">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1003629 に移動します][CR1003629]。</span><span class="sxs-lookup"><span data-stu-id="e7809-197">To review the history of this feature in the Chromium open-source project, navigate to Issue [1003629][CR1003629].</span></span>  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="要素ツールのコンテキスト メニューで強調表示されているキャプチャ ノードのスクリーンショット" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   <span data-ttu-id="e7809-199">**要素ツールの** コンテキスト メニューで強調表示されているキャプチャ ノード **の** スクリーンショット</span><span class="sxs-lookup"><span data-stu-id="e7809-199">**Capture node screenshot** highlighted on the context menu in the **Elements** tool</span></span>  
:::image-end:::  

### <span data-ttu-id="e7809-200">要素ツールの更新</span><span class="sxs-lookup"><span data-stu-id="e7809-200">Elements tool updates</span></span>  

#### <span data-ttu-id="e7809-201">:target CSS 状態の適用のサポート</span><span class="sxs-lookup"><span data-stu-id="e7809-201">Support forcing the :target CSS state</span></span>  

<span data-ttu-id="e7809-202">DevTools を使って [、:target][MdnDocsWebCssTarget] CSS 擬似クラスを強制的に使う場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7809-202">You may now use DevTools to force the [:target][MdnDocsWebCssTarget] CSS pseudo-class.</span></span>  <span data-ttu-id="e7809-203">擬似クラスは、一意の要素 \(target element\) に URL のフラグメントと一致する要素がある `:target` `id` 場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="e7809-203">The `:target` pseudo-class is triggered when a unique element \(the target element\) has an `id` that matches a fragment of the URL.</span></span>  <span data-ttu-id="e7809-204">たとえば、URL は `http://www.example.com/index.html#section1` HTML 要素で擬似クラスを `:target` トリガーします `id="section1"` 。</span><span class="sxs-lookup"><span data-stu-id="e7809-204">For example, the `http://www.example.com/index.html#section1` URL triggers the `:target` pseudo-class on an HTML element with `id="section1"`.</span></span>  <span data-ttu-id="e7809-205">セクション 1 が強調表示されているデモを試す場合は [、CSS :target デモに移動します][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]。</span><span class="sxs-lookup"><span data-stu-id="e7809-205">To try a demo with section 1 highlighted, navigate to [CSS :target demo][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1].</span></span>  <span data-ttu-id="e7809-206">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1156628][CR1156628]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-206">To review the history of this feature in the Chromium open-source project, navigate to Issue [1156628][CR1156628].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="強制 CSS がない Web ページが強調表示されている" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         <span data-ttu-id="e7809-208">強制 CSS を使用して強調表示された Web ページ</span><span class="sxs-lookup"><span data-stu-id="e7809-208">Webpage highlighted with no forced CSS</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text=":target CSS forced and web-highlighted" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` <span data-ttu-id="e7809-210">CSS の強制と Web ページの強調表示</span><span class="sxs-lookup"><span data-stu-id="e7809-210">CSS forced and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="e7809-211">Duplicate 要素を使用して要素をコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-211">Use Duplicate elements to copy elements</span></span>  

<span data-ttu-id="e7809-212">新しい **Duplicate 要素ショートカットを使用して** 、要素を複製します。</span><span class="sxs-lookup"><span data-stu-id="e7809-212">Use the new **Duplicate element** shortcut to clone an element.</span></span>  <span data-ttu-id="e7809-213">要素ツール **で要素** をポイントし、コンテキスト メニュー \(右クリック\) を開き、[要素の複製] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7809-213">In the **Elements** tool, hover on an element, open the contextual menu \(right-click\), choose **Duplicate element**.</span></span>  <span data-ttu-id="e7809-214">選択した要素の下に新しい要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-214">A new element is created under the selected element.</span></span>  <span data-ttu-id="e7809-215">キーボード ショートカットで要素を複製するには `Shift` + `Alt` + `Down Arrow` 、\(Windows/Linux\) または `Shift` + `Option` + `Down Arrow` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-215">To duplicate the element with a keyboard shortcut, select `Shift`+`Alt`+`Down Arrow` \(Windows/Linux\) or `Shift`+`Option`+`Down Arrow` \(macOS\).</span></span>  <span data-ttu-id="e7809-216">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1150797 に移動します][CR1150797]。</span><span class="sxs-lookup"><span data-stu-id="e7809-216">To review the history of this feature in the Chromium open-source project, navigate to Issue [1150797][CR1150797].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="要素ツールの要素のコンテキスト メニューで Duplicate 要素が強調表示されている" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   <span data-ttu-id="e7809-218">**要素ツールの**要素のコンテキスト メニューで Duplicate 要素が**強調表示**されている</span><span class="sxs-lookup"><span data-stu-id="e7809-218">The **Duplicate element** is highlighted in the context menu on an element in the **Elements** tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="e7809-219">カスタム CSS プロパティのカラー ピッカー</span><span class="sxs-lookup"><span data-stu-id="e7809-219">Color pickers for custom CSS properties</span></span>  

<span data-ttu-id="e7809-220">[ **スタイル]** ウィンドウに、カスタム CSS プロパティのカラー ピッカーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-220">The **Styles** pane now displays color pickers for custom CSS properties.</span></span>  <span data-ttu-id="e7809-221">色の値の RGBA、HSLA、および Hex 形式を循環するには、カラー ピッカーを長押 `Shift` しして選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-221">To cycle through the RGBA, HSLA, and Hex formats of the color value, hold `Shift` and choose the color picker.</span></span>  <span data-ttu-id="e7809-222">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1147016][CR1147016]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-222">To review the history of this feature in the Chromium open-source project, navigate to Issue [1147016][CR1147016].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="カスタム CSS プロパティのカラー ピッカー" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   <span data-ttu-id="e7809-224">カスタム CSS プロパティのカラー ピッカー</span><span class="sxs-lookup"><span data-stu-id="e7809-224">Color pickers for custom CSS properties</span></span>  
:::image-end:::  

#### <span data-ttu-id="e7809-225">CSS クラスとプロパティをコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-225">Copy CSS classes and properties</span></span>  

<span data-ttu-id="e7809-226">コンテキスト メニューのいくつかの新しいオプションを使用して、CSS プロパティを迅速にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e7809-226">You may now copy CSS properties quicker with a few new options in the contextual menu.</span></span>  <span data-ttu-id="e7809-227">要素ツール **で** 、要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-227">In the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="e7809-228">値をコピーするには、[スタイル]\*\*\*\* ウィンドウで、CSS クラスまたは CSS プロパティをポイントし、コンテキスト メニュー \(右クリック\) を開き、コピー オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-228">To copy the value, in the **Styles** pane, hover on a CSS class or a CSS property, open a contextual menu \(right-click\), and choose the copy option.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e7809-229">CSS クラスのオプションをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-229">Copy options for a CSS class.</span></span>  
      
      | <span data-ttu-id="e7809-230">オプション</span><span class="sxs-lookup"><span data-stu-id="e7809-230">Option</span></span> | <span data-ttu-id="e7809-231">詳細</span><span class="sxs-lookup"><span data-stu-id="e7809-231">Details</span></span> |  
      |:--- |:--- |  
      | **<span data-ttu-id="e7809-232">コピー セレクター</span><span class="sxs-lookup"><span data-stu-id="e7809-232">Copy selector</span></span>** | <span data-ttu-id="e7809-233">現在のセレクター名をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-233">Copy the current selector name.</span></span> |  
      | **<span data-ttu-id="e7809-234">ルールをコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-234">Copy rule</span></span>** | <span data-ttu-id="e7809-235">現在のセレクターのルールをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-235">Copy the rule of the current selector.</span></span> |  
      | **<span data-ttu-id="e7809-236">すべての宣言をコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-236">Copy all declarations</span></span>** | <span data-ttu-id="e7809-237">無効なプロパティとプレフィックス付きプロパティを含む、現在のルールのすべての宣言をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-237">Copy all declarations under the current rule, including non-valid and prefixed properties.</span></span> |  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e7809-238">CSS プロパティのオプションをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-238">Copy options for a CSS property.</span></span>  
      
      | <span data-ttu-id="e7809-239">オプション</span><span class="sxs-lookup"><span data-stu-id="e7809-239">Option</span></span> | <span data-ttu-id="e7809-240">詳細</span><span class="sxs-lookup"><span data-stu-id="e7809-240">Details</span></span> |      
      |:--- |:--- |  
      | **<span data-ttu-id="e7809-241">宣言をコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-241">Copy declaration</span></span>** | <span data-ttu-id="e7809-242">現在の行の宣言をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-242">Copy the declaration of the current line.</span></span> |  
      | **<span data-ttu-id="e7809-243">Copy プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7809-243">Copy property</span></span>** | <span data-ttu-id="e7809-244">現在の行のプロパティをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-244">Copy the property of the current line.</span></span> |  
      | **<span data-ttu-id="e7809-245">値をコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-245">Copy value</span></span>** | <span data-ttu-id="e7809-246">現在の行の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7809-246">Copy the value of the current line.</span></span> |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="コンテキスト メニューの CSS クラスのコピー オプション" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         <span data-ttu-id="e7809-248">コンテキスト メニューの CSS クラスのコピー オプション</span><span class="sxs-lookup"><span data-stu-id="e7809-248">Copy options for a CSS class in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="コンテキスト メニューの CSS プロパティのオプションをコピーする" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         <span data-ttu-id="e7809-250">コンテキスト メニューの CSS プロパティのコピー オプション</span><span class="sxs-lookup"><span data-stu-id="e7809-250">Copy options for a CSS property in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e7809-251">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1152391 に移動します][CR1152391]。</span><span class="sxs-lookup"><span data-stu-id="e7809-251">To review the history of this feature in the Chromium open-source project, navigate to Issue [1152391][CR1152391].</span></span>  

### <span data-ttu-id="e7809-252">Cookie の更新</span><span class="sxs-lookup"><span data-stu-id="e7809-252">Cookies updates</span></span>  

#### <span data-ttu-id="e7809-253">URL デコードされた Cookie を表示する新しいオプション</span><span class="sxs-lookup"><span data-stu-id="e7809-253">New option to display URL-decoded cookies</span></span>  

<span data-ttu-id="e7809-254">これで、[Cookie] ウィンドウに URL デコードされた Cookie の **値を表示** できます。</span><span class="sxs-lookup"><span data-stu-id="e7809-254">You may now opt to display the URL-decoded cookies value in the **Cookies** pane.</span></span>  <span data-ttu-id="e7809-255">デコードされた Cookie を表示するには、[**アプリケーション**Cookie] ウィンドウに移動し、一覧から任意の Cookie を選択し、[デコードされた URL を表示する] の横にあるチェック  >  \*\*\*\*\*\*ボックスをオンにします\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7809-255">To display the decoded cookie, navigate to **Application** > **Cookies** pane, choose any cookie on the list, and choose the checkbox next to **Show URL decoded**.</span></span>  <span data-ttu-id="e7809-256">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [997625][CR997625]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-256">To review the history of this feature in the Chromium open-source project, navigate to Issue [997625][CR997625].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="URL デコードされた Cookie を表示するオプション" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   <span data-ttu-id="e7809-258">URL デコードされた Cookie を表示するオプション</span><span class="sxs-lookup"><span data-stu-id="e7809-258">Option to display URL decoded cookies</span></span>  
:::image-end:::  

#### <span data-ttu-id="e7809-259">表示されている Cookie のフィルター処理とクリア</span><span class="sxs-lookup"><span data-stu-id="e7809-259">Filter and clear visible cookies</span></span>  

<span data-ttu-id="e7809-260">Microsoft Edge バージョン 88 以前\*\*\*\* では、アプリケーション ツールは、[すべての Cookie をクリア] ボタンを使用してすべての Cookie をクリアする方法**のみを提供**しました。</span><span class="sxs-lookup"><span data-stu-id="e7809-260">In Microsoft Edge version 88 or earlier, the **Application** tool only provided a way to clear all cookies with the **Clear all cookies** button.</span></span>  <span data-ttu-id="e7809-261">Microsoft Edge バージョン 89 では、[\*\*\*\* フィルター処理された Cookie のクリア] を選択して、フィルター処理された Cookie のみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="e7809-261">In Microsoft Edge version 89, you may now choose **Clear filtered cookies** to delete only the filtered cookies.</span></span>  <span data-ttu-id="e7809-262">Cookie をフィルター処理するには、[**アプリケーション Cookie] に**  >  **移動**し、[フィルター] テキスト ボックス**に**入力します。</span><span class="sxs-lookup"><span data-stu-id="e7809-262">To filter cookies, navigate to **Application** > **Cookies**, and type in the **Filter** textbox.</span></span>  <span data-ttu-id="e7809-263">表示された Cookie を削除するには、[フィルター処理された Cookie のクリア **] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="e7809-263">To delete the displayed cookies, choose the **Clear filtered cookies** button.</span></span>  <span data-ttu-id="e7809-264">他のすべての Cookie を表示するには、フィルター テキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="e7809-264">To display all other cookies, clear the filter text.</span></span>  <span data-ttu-id="e7809-265">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [978059 に移動します][CR978059]。</span><span class="sxs-lookup"><span data-stu-id="e7809-265">To review the history of this feature in the Chromium open-source project, navigate to Issue [978059][CR978059].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="表示されている Cookie のみをクリアする" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   <span data-ttu-id="e7809-267">表示されている Cookie のみをクリアする</span><span class="sxs-lookup"><span data-stu-id="e7809-267">Clear only visible cookies</span></span>  
:::image-end:::  

#### <span data-ttu-id="e7809-268">ストレージ ウィンドウでサード パーティの Cookie をクリアする新しいオプション</span><span class="sxs-lookup"><span data-stu-id="e7809-268">New option to clear third-party cookies in the Storage pane</span></span>  

<span data-ttu-id="e7809-269">DevTools は、既定でファースト パーティの Cookie のみをクリアします。</span><span class="sxs-lookup"><span data-stu-id="e7809-269">DevTools now clear only first-party cookies by default.</span></span>  <span data-ttu-id="e7809-270">Web サイトのデータとファースト パーティの Cookie のみをクリアするには、[**アプリケーション**ストレージ] に移動し、[サイト データのクリア]  >  \*\*\*\*\*\*を選択します\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7809-270">To clear website data and first-party cookies only, navigate to **Application** > **Storage**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="e7809-271">Web サイトのデータとすべての Cookie をクリアするには、[アプリケーション ストレージ]**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="e7809-271">To clear website data and all cookies, navigate to **Application** > **Storage**.</span></span>  <span data-ttu-id="e7809-272">[サード パーティの Cookie **を含む**] の横にあるチェック ボックスをオンにし、[サイト データのクリア **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7809-272">Choose the checkbox next to **including third-party cookies**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="e7809-273">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1012337 に移動します][CR1012337]。</span><span class="sxs-lookup"><span data-stu-id="e7809-273">To review the history of this feature in the Chromium open-source project, navigate to Issue [1012337][CR1012337].</span></span>  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="サード パーティの Cookie をクリアするオプション" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   <span data-ttu-id="e7809-275">サード パーティの Cookie をクリアするオプション</span><span class="sxs-lookup"><span data-stu-id="e7809-275">Option to clear third-party cookies</span></span>  
:::image-end:::  

### <span data-ttu-id="e7809-276">ネットワーク ツールの更新</span><span class="sxs-lookup"><span data-stu-id="e7809-276">Network tool updates</span></span>  

#### <span data-ttu-id="e7809-277">[レコードの保持] ネットワーク ログの設定</span><span class="sxs-lookup"><span data-stu-id="e7809-277">Persist Record network log setting</span></span>  

<span data-ttu-id="e7809-278">Microsoft Edge バージョン 88 以前では、DevTools は Web ページが更新された際に **Record** ネットワーク ログ設定をリセットします。</span><span class="sxs-lookup"><span data-stu-id="e7809-278">In Microsoft Edge version 88 or earlier, DevTools reset the **Record network log** setting when a webpage refreshes.</span></span>  <span data-ttu-id="e7809-279">Microsoft Edge バージョン 89 では、DevTools はレコード ネットワーク ログの **設定を保持** します。</span><span class="sxs-lookup"><span data-stu-id="e7809-279">In Microsoft Edge version 89, DevTools now persist the **Record network log** setting.</span></span>  <span data-ttu-id="e7809-280">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1122580][CR1122580]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-280">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122580][CR1122580].</span></span>  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="ネットワーク ログを記録する" lightbox="../../media/2021/01/network-log.msft.png":::
   <span data-ttu-id="e7809-282">ネットワーク ログを記録する</span><span class="sxs-lookup"><span data-stu-id="e7809-282">Record network log</span></span>  
:::image-end:::  

#### <span data-ttu-id="e7809-283">オンライン オプションが調整オプションなし</span><span class="sxs-lookup"><span data-stu-id="e7809-283">Online option is now No throttling option</span></span>  

<span data-ttu-id="e7809-284">ネットワーク エミュレーション オプション **Online の** 名前が [調整なし] **に変更されました**。</span><span class="sxs-lookup"><span data-stu-id="e7809-284">The network emulation option **Online** is now renamed to **No Throttling**.</span></span>  <span data-ttu-id="e7809-285">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1028078 に移動します][CR1028078]。</span><span class="sxs-lookup"><span data-stu-id="e7809-285">To review the history of this feature in the Chromium open-source project, navigate to Issue [1028078][CR1028078].</span></span>  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="調整オプションなし" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   <span data-ttu-id="e7809-287">**調整オプション** なし</span><span class="sxs-lookup"><span data-stu-id="e7809-287">**No throttling** option</span></span>  
:::image-end:::  

### <span data-ttu-id="e7809-288">コンソール ツール、ソース ツール、および [スタイル] ウィンドウの新しいコピー オプション</span><span class="sxs-lookup"><span data-stu-id="e7809-288">New copy options in the Console tool, Sources tool, and Styles pane</span></span>

#### <span data-ttu-id="e7809-289">コンソール ツールとソース ツールでオブジェクトをコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-289">Copy object in the Console and Sources tool</span></span>  

<span data-ttu-id="e7809-290">コンソール ツールとソース ツールでオブジェクトの **値** を **コピー** できます。</span><span class="sxs-lookup"><span data-stu-id="e7809-290">You may now copy object values in the **Console** and **Sources** tools.</span></span>  <span data-ttu-id="e7809-291">オブジェクト値をコピーする機能は、大きなオブジェクトを操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e7809-291">The ability to copy object values is useful when working with large objects.</span></span>  <span data-ttu-id="e7809-292">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[問題 [1148353]][CR1148353] および [[1149859]][CR1149859]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-292">To review the history of this feature in the Chromium open-source project, navigate to Issues [1148353][CR1148353] and [1149859][CR1149859].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e7809-293">コンソール ツール **でオブジェクト** をポイントし、コンテキスト メニュー \(右クリック\) を開き、[オブジェクトのコピー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7809-293">In the **Console** tool, hover on an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e7809-294">ソース**ツールの**ブレークポイントで、オブジェクトをポイントし、[オブジェクト] ポップアップ\*\*\*\* ウィンドウでオブジェクトを強調表示し、コンテキスト メニュー \(右クリック\) を開き、[オブジェクトのコピー] を選択**します。**</span><span class="sxs-lookup"><span data-stu-id="e7809-294">In the **Sources** tool, on a breakpoint, hover on an object, in the **Object** popup window, highlight an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="コンソールでオブジェクトをコピーする" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         <span data-ttu-id="e7809-296">コンソールでオブジェクトをコピー **する**</span><span class="sxs-lookup"><span data-stu-id="e7809-296">Copy object in the **Console**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="Sources のオブジェクトをコピーする" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         <span data-ttu-id="e7809-298">Sources の **オブジェクトをコピーする**</span><span class="sxs-lookup"><span data-stu-id="e7809-298">Copy object in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="e7809-299">[ソース] ツールと [スタイル] ウィンドウでファイル名をコピーする</span><span class="sxs-lookup"><span data-stu-id="e7809-299">Copy file name in the Sources tool and Styles pane</span></span>  

<span data-ttu-id="e7809-300">コンテキスト メニューを使用してファイル名をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e7809-300">You may now copy a file name using the contextual menu.</span></span>  <span data-ttu-id="e7809-301">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[問題 [1155120] に移動します][CR1155120]。</span><span class="sxs-lookup"><span data-stu-id="e7809-301">To review the history of this feature in the Chromium open-source project, navigate to Issues [1155120][CR1155120].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e7809-302">ソース ツール **で、** ファイル名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[ファイル名のコピー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7809-302">In the **Sources** tool, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e7809-303">[ **要素]** ツールの [> **スタイル** ] ウィンドウで、ファイル名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[ファイル名のコピー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7809-303">In the **Elements** tool > **Styles** pane, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="Sources のファイル名をコピーする" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         <span data-ttu-id="e7809-305">Sources のファイル名 **をコピーする**</span><span class="sxs-lookup"><span data-stu-id="e7809-305">Copy file name in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="[スタイル] ウィンドウでファイル名をコピーする" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         <span data-ttu-id="e7809-307">[スタイル] ウィンドウでファイル名 **をコピー** する</span><span class="sxs-lookup"><span data-stu-id="e7809-307">Copy file name in **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="e7809-308">フレームの詳細の更新</span><span class="sxs-lookup"><span data-stu-id="e7809-308">Updates to Frame details</span></span>  

#### <span data-ttu-id="e7809-309">フレームの詳細のサービス ワーカー情報</span><span class="sxs-lookup"><span data-stu-id="e7809-309">Service Workers information in Frame details</span></span>  

<span data-ttu-id="e7809-310">DevTools では、親フレームの下に専用のサービス ワーカーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-310">DevTools now lists a dedicated service worker under the parent frame.</span></span>  <span data-ttu-id="e7809-311">次の図では、サービス ワーカーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-311">In the following figure, service worker details are displayed.</span></span>  <span data-ttu-id="e7809-312">サービス ワーカーの詳細を表示するには **、[Application**Frames Service Workers] に移動し、サービス  >  \*\*\*\*  >  `top`  >  \*\*\*\* ワーカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7809-312">To display the service worker details, navigate to **Application** > **Frames** > `top` > **Service Workers** and then choose a service worker.</span></span>  <span data-ttu-id="e7809-313">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1122507 に移動します][CR1122507]。</span><span class="sxs-lookup"><span data-stu-id="e7809-313">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122507][CR1122507].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="フレームの詳細のサービス ワーカー情報" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   <span data-ttu-id="e7809-315">**フレームの詳細**のサービス ワーカー**情報**</span><span class="sxs-lookup"><span data-stu-id="e7809-315">**Service Workers** information in the **Frames** details</span></span>  
:::image-end:::  

#### <span data-ttu-id="e7809-316">フレームの詳細でメモリ情報を測定する</span><span class="sxs-lookup"><span data-stu-id="e7809-316">Measure Memory information in Frame details</span></span>  

<span data-ttu-id="e7809-317">API `performance.measureMemory()` の状態が[API の可用性] セクション **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-317">The `performance.measureMemory()` API status is now displayed under the **API availability** section.</span></span>  <span data-ttu-id="e7809-318">新しい `performance.measureMemory()` API は、Web ページ全体のメモリ使用量を見積もっています。</span><span class="sxs-lookup"><span data-stu-id="e7809-318">The new `performance.measureMemory()` API estimates the memory usage of the entire webpage.</span></span>  <span data-ttu-id="e7809-319">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1139899 に移動します][CR1139899]。</span><span class="sxs-lookup"><span data-stu-id="e7809-319">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="メモリを測定する" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   <span data-ttu-id="e7809-321">メモリを測定する</span><span class="sxs-lookup"><span data-stu-id="e7809-321">Measure Memory</span></span>  
:::image-end:::  

### <span data-ttu-id="e7809-322">パフォーマンス ツールでフレームがドロップされました</span><span class="sxs-lookup"><span data-stu-id="e7809-322">Dropped frames in the Performance tool</span></span>  

<span data-ttu-id="e7809-323">パフォーマンス ツール [で読み込みパフォーマンスを分析][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]すると **、[Frames]** セクションでドロップされたフレームが赤としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="e7809-323">When you [analyze load performance in the Performance tool][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance], the **Frames** section now marks dropped frames as red.</span></span>  <span data-ttu-id="e7809-324">フレーム レートを表示するには、ドロップしたフレームにマウス ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-324">To display the frame rate, hover on a dropped frame.</span></span>  <span data-ttu-id="e7809-325">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1075865][CR1075865]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7809-325">To review the history of this feature in the Chromium open-source project, navigate to Issue [1075865][CR1075865].</span></span>  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="破棄されたフレーム" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   <span data-ttu-id="e7809-327">破棄されたフレーム</span><span class="sxs-lookup"><span data-stu-id="e7809-327">Dropped frames</span></span>  
:::image-end:::  

#### <span data-ttu-id="e7809-328">新しいカラー コントラスト計算 - 高度な知覚コントラスト アルゴリズム (APCA)</span><span class="sxs-lookup"><span data-stu-id="e7809-328">New color contrast calculation - Advanced Perceptual Contrast Algorithm (APCA)</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="e7809-329">色の選択で[AA][W3cWaiWcag21QuickrefContrastMinimum]AAA ガイドラインのコントラスト比を置き換える[APCA (Advanced Perceptual Contrast Algorithm)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] / [][W3cWaiWcag21QuickrefContrastEnhanced][です][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]。</span><span class="sxs-lookup"><span data-stu-id="e7809-329">The [Advanced Perceptual Contrast Algorithm (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] replaces the [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] guidelines contrast ratio in the [Color Picker][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker].</span></span>  <span data-ttu-id="e7809-330">APCA は、コントラストを計算する新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="e7809-330">APCA is a new way to compute contrast.</span></span>  <span data-ttu-id="e7809-331">色の認識に関する最新の調査に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-331">It is based on modern research on color perception.</span></span>  <span data-ttu-id="e7809-332">AA/AAA ガイドラインと比較すると、APCA はコンテキストに依存します。</span><span class="sxs-lookup"><span data-stu-id="e7809-332">Compared to AA/AAA guidelines, APCA is more context-dependent.</span></span>  <span data-ttu-id="e7809-333">コントラストは、テキスト、色、コンテキストの次の空間プロパティに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="e7809-333">The contrast is calculated based on the following spatial properties of the text, color, and context.</span></span>  

*   <span data-ttu-id="e7809-334">フォントの太さおよびサイズを含むテキストの空間プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e7809-334">Spatial properties of text that include font weight and size.</span></span>  
*   <span data-ttu-id="e7809-335">テキストと背景のコントラストを含む色の空間プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e7809-335">Spatial properties of color that include perceived contrast between text and background.</span></span>  
*   <span data-ttu-id="e7809-336">環境光、周囲、および目的を含むコンテキストの空間プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e7809-336">Spatial properties of context that include ambient light, surroundings, and intended purpose.</span></span>  
    
<span data-ttu-id="e7809-337">この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、[新しい高度な視聴覚コントラスト アルゴリズム (APCA) を有効にする] の横にあるチェック ボックスをオンにして、以前のコントラスト比と  >  \*\*\*\*\*\*AA/AAA\*\*ガイドラインに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="e7809-337">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable new Advanced Perceptual Contrast Algorithm (APCA) replacing previous contrast ratio and AA/AAA guidelines**.</span></span>  <span data-ttu-id="e7809-338">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1121900 に移動します][CR1121900]。</span><span class="sxs-lookup"><span data-stu-id="e7809-338">To review the history of this feature in the Chromium open-source project, navigate to Issue [1121900][CR1121900].</span></span>  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="カラー ピッカーの APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   <span data-ttu-id="e7809-340">カラー ピッカーの APCA</span><span class="sxs-lookup"><span data-stu-id="e7809-340">APCA in the Color Picker</span></span>  
:::image-end:::  

## <span data-ttu-id="e7809-341">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e7809-341">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="e7809-342">Windows、Linux、または macOS を使用している場合は、 [既定][MicrosoftEdgePreviewChannels] の開発ブラウザーとして Microsoft Edge プレビュー チャネルの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e7809-342">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="e7809-343">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e7809-343">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="e7809-344">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="e7809-344">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "DevTools (Microsoft Edge 85) の新機能 |Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "色の選択コントロールのテキスト要素のコントラスト比を表示する - ユーザー補助|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "CSS の変更 - CSS 参照|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "折りたたみ可能なデュアルスクリーン デバイスでのテスト - Microsoft Edge DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレート|Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートをシミュレートする - Microsoft Edge DevTools アプリケーションでモバイル デバイスをエミュレート|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "レコード読み込みパフォーマンス - パフォーマンス分析リファレンス |Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "DevTools ページの [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 開発者ツールの概要|Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "セクション 1 - DevTools の新機能 (Microsoft Edge 89) の CSS :target デモ|GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "プル 229: 設定にドロップダウンを実装してテーマを変更|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "プル 233: 依存関係オブジェクトとして Microsoft Edge のデバッガーを含|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "プル 235: Edge DevTools バージョンを 85.0.564.40 バージョンにアップグレード|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "プル 248: インスタンス パネルに 1 つの閉じるボタンを追加|GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "フォントの特性と背景の色を選択して、読みやすさを向上するために十分なコントラスト|W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "信頼できる型|W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface の新しい |Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - Extension Marketplace |Visual Studio コード"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge アプリケーションのデバッガー|Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  
[CR978059]: https://crbug.com/978059 "問題 978059: Cookie をフィルター処理するときに削除し、フィルター処理された Cookie とフィルター処理された cookie |Chromium のバグ"  
[CR997625]: https://crbug.com/997625 "問題 997625: 新機能 Req |Cookie で URL デコードされた値を表示するオプションが必要|Chromium のバグ"  
[CR1003629]: https://crbug.com/1003629 "問題 1003629: キャプチャ ノードでは、2 つ折り下のノードのスクリーンショットが表示されません。|Chromium のバグ"  
[CR1012337]: https://crbug.com/1012337 "問題 1012337: サイト データをクリアすると、Google 以外のサイトで Google セッションが破棄|Chromium のバグ"  
[CR1028078]: https://crbug.com/1028078 "問題 1028078: [オンライン] と [オフライン] をリスト 内の横に置|Chromium のバグ"  
[CR1054281]: https://crbug.com/1054281 "問題 1054281: 機能要求: DevTools は、折りたたみ可能なデュアルスクリーン デバイスをエミュレートする必要|Chromium のバグ"  
[CR1075865]: https://crbug.com/1075865 "問題 1075865: devtools タイムラインにドロップ されたフレームを表示|Chromium のバグ"  
[CR1093229]: https://crbug.com/1093229 "問題 1093229: DevTools: 特殊な書体エディター UI インターフェイスを提供|Chromium のバグ"  
[CR1121900]: https://crbug.com/1121900 "問題 1121900: DevTools: 新しい仕様ごとにコントラスト計算ロジックを更新|Chromium のバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレーム ツリー ビューでの Surface ワーカー情報 | Chromium のバグ"  
[CR1122580]: https://crbug.com/1122580 "問題 1122580: 再読み込み時にネットワーク記録を無効|Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox ツール | Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレーム詳細ビューでゲート API の可用性を報告する | Chromium のバグ"  
[CR1139949]: https://crbug.com/1139949 "問題 1139949: Flexbox オーバーレイ |Chromium のバグ"  
[CR1147016]: https://crbug.com/1147016 "問題 1147016: カラー ピッカーが var() 関数に表示されません。|Chromium のバグ"  
[CR1148353]: https://crbug.com/1148353 "問題 1148353: 機能要求: devtools コンソール からオブジェクトをコピー|Chromium のバグ"  
[CR1149859]: https://crbug.com/1149859 "問題 1149859: [feature request][Console] add copy object to clipboard item to contextual menu |Chromium のバグ"  
[CR1150797]: https://crbug.com/1150797 "問題 1150797: [要素] パネルの [要素] メニューに要素のショートカット メニューを追加|Chromium のバグ"  
[CR1152391]: https://crbug.com/1152391 "問題 1152391: スタイル パネル ウィンドウでの CSS ショートカット メニューのコピーの|Chromium のバグ"  
[CR1155120]: https://crbug.com/1155120 "問題 1155120: [FR]ファイル名と行番号のコピーをサポート|Chromium のバグ"  
[CR1156628]: https://crbug.com/1156628 "問題 1156628: DevTools: :target in force 要素状態機能のサポートを追加|Chromium のバグ"  
[CR1157329]: https://crbug.com/1157329 "問題 1157329: アクセシビリティ - ナレーター: ナレーターが[スタイル] タブ の [スタイル] タブのコードで使用可能な候補の数と位置を発表|Chromium のバグ"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target ":target |MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "Contrast (拡張) - WCAG を満たす方法 (クイック リファレンス) |W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "Contrast (最小) - WCAG を満たす方法 (クイック リファレンス) |W3C"  

> [!NOTE]
> <span data-ttu-id="e7809-399">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="e7809-399">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e7809-400">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2021/01/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="e7809-400">The original page is found [here](https://developers.google.com/web/updates/2021/01/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e7809-402">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e7809-402">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "スパン プレースホルダー"  
