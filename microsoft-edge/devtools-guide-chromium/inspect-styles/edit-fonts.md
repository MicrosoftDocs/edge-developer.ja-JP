---
description: Microsoft Edge DevTools の [スタイル] ウィンドウを使用して CSS フォントのスタイルと設定を変更する方法について説明します。
title: DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/03/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 928f7abb0f74839708cbe5c904ad321109ae33f0
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313263"
---
# <span data-ttu-id="3c542-104">[スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する</span><span class="sxs-lookup"><span data-stu-id="3c542-104">Edit CSS font styles and settings in the Styles pane</span></span>  

:::image type="icon" source="../media/experimental-tag-14px.msft.png":::

<span data-ttu-id="3c542-105">Web 上の文字体裁は、ユーザー エクスペリエンスの重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="3c542-105">Typography on the web is an important part of the user experience.</span></span>  <span data-ttu-id="3c542-106">企業のブランド ガイドラインを満たして、さまざまなデバイスでコンテンツが期待通り表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c542-106">You want to ensure you meet corporate brand guidelines, and your content displays as expected on various devices.</span></span>  <span data-ttu-id="3c542-107">テキストは、サイズと行の高さを使用して読みやすくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c542-107">Text must be easy to read using size and line-height.</span></span>  <span data-ttu-id="3c542-108">ユーザーは、個々のニーズに合わせてフォントのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3c542-108">Users may resize fonts to meet individual needs.</span></span>  <span data-ttu-id="3c542-109">ユーザー デバイスで特定のフォントを使用できない場合は、フォールバック フォント オプションを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c542-109">For situations when specific fonts are not available on a user device, you should provide fallback font options.</span></span>  

<span data-ttu-id="3c542-110">CSS は、最近の文字体裁をより良くサポートします。</span><span class="sxs-lookup"><span data-stu-id="3c542-110">CSS provides better support for typography in recent years.</span></span>  <span data-ttu-id="3c542-111">テキストのサイズを定義するには、多数の異なる CSS 単位を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c542-111">There are dozens of different CSS units available to define the size of text.</span></span>  <span data-ttu-id="3c542-112">また、フォント サイズ、間隔、行の高さ、その他の入力ミス機能に影響を与えるいくつかの CSS プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="3c542-112">You also have several CSS properties that affect font-size, spacing, line height, and other typographic features.</span></span>  

<span data-ttu-id="3c542-113">文字体裁を簡単に操作するために、表示フォント\*\*\*\* エディターが [スタイル] ウィンドウ**に表示**されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-113">To make it easier when working with typography, a visual **Font Editor** is now in the **Styles** pane.</span></span>  <span data-ttu-id="3c542-114">フォント設定を変更すると、変更がブラウザーに即座にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="3c542-114">You may change your font settings, and the changes are rendered immediately in the browser.</span></span>  <span data-ttu-id="3c542-115">すべて、CSS に関する詳細な知識がない。</span><span class="sxs-lookup"><span data-stu-id="3c542-115">All without in-depth knowledge of CSS.</span></span>  

<span data-ttu-id="3c542-116">現在、[スタイル **] ウィンドウ機能内** の [新しいフォント エディターを有効にする] ツールは試験的であり [、Microsoft Edge 開発者][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]ツールで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c542-116">Currently the **Enable new font editor tool within the Styles pane** feature is experimental and you need to [turn it on for Microsoft Edge Developer Tools][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures].</span></span>  

<span data-ttu-id="3c542-117">[スタイル] ウィンドウ **の CSS** (フォント定義またはインライン スタイル) には、視覚的なフォント エディターを開くアイコンが自動的に **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="3c542-117">Any CSS in the **Styles** pane, either font definitions or inline styles, automatically displays an icon that opens the visual **Font Editor**.</span></span>  <span data-ttu-id="3c542-118">ビジュアル フォント エディターを **開く場合は**、[フォント エディター **] アイコンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3c542-118">To open the visual **Font Editor**, choose the **Font Editor** icon.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-icon.msft.png" alt-text="フォント設定を編集する [スタイル] ウィンドウのアイコン" lightbox="../media/font-editor-icon.msft.png":::
         <span data-ttu-id="3c542-120">フォント設定を編集 **する [** スタイル] ウィンドウのアイコン</span><span class="sxs-lookup"><span data-stu-id="3c542-120">The icon in the **Styles** pane to edit font settings</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-open.msft.png" alt-text="[スタイル] ウィンドウの上部に表示されるフォント エディター" lightbox="../media/font-editor-open.msft.png":::
         <span data-ttu-id="3c542-122">[ **スタイル] ウィンドウ** の上部にフォント エディター **が開** きます。</span><span class="sxs-lookup"><span data-stu-id="3c542-122">The **Font Editor** open on top of the **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3c542-123">ビジュアル フォント エディターのすべてのフィールド **は、[** スタイル] ウィンドウの CSS の値から **設定** されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-123">All fields in the visual **Font Editor** are populated from the values in the CSS in the **Styles** pane.</span></span>  <span data-ttu-id="3c542-124">たとえば、[スタイル] ウィンドウで定義を設定すると、行の高さテキスト フィールドが表示され、単位ドロップダウン `line-height` `160%` \*\*\*\* `160` が表示されます `%` 。</span><span class="sxs-lookup"><span data-stu-id="3c542-124">For example, the `line-height` definition is set to `160%` in the **Styles** pane, so the line height text field displays `160`, and the unit dropdown displays `%`.</span></span>  <span data-ttu-id="3c542-125">また、スライダーはテキスト フィールドの値と一致する設定に自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-125">Also, the slider is automatically set to match the values of the text field.</span></span>  

<span data-ttu-id="3c542-126">フォント **エディターは、** フォント ファミリ セレクターと CSS プロパティ エディターの 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-126">The **Font Editor** consists of two parts:  the Font Family selector, and the CSS Properties editor.</span></span>  

## <span data-ttu-id="3c542-127">フォント ファミリ セレクター</span><span class="sxs-lookup"><span data-stu-id="3c542-127">The Font Family selector</span></span>  

<span data-ttu-id="3c542-128">フォント ファミリ セレクターは、ビジュアル フォント エディターの **上部です**。</span><span class="sxs-lookup"><span data-stu-id="3c542-128">The Font Family selector is the upper part of the visual **Font Editor**.</span></span>  <span data-ttu-id="3c542-129">CSS ルールのフォントを選択するには、CSS エディターでフォント ファミリ **セレクターを使用** します。</span><span class="sxs-lookup"><span data-stu-id="3c542-129">To choose the fonts of the CSS rule, in the CSS editor, use the **Font Family** selector.</span></span>  <span data-ttu-id="3c542-130">CSS ルールごとにメインフォントとフォールバック フォントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3c542-130">You may choose main and fallback fonts for each CSS rule.</span></span>  

:::image type="complex" source="../media/font-editor-font-family.msft.png" alt-text="[スタイル] ウィンドウの上部でフォント エディターが開き、フォント ファミリ セレクターが強調表示されている" lightbox="../media/font-editor-font-family.msft.png":::
   <span data-ttu-id="3c542-132">[ **スタイル] ウィンドウの** 上部でフォント エディター **が開** き、フォント ファミリ **セレクターが** 強調表示されている</span><span class="sxs-lookup"><span data-stu-id="3c542-132">The **Font Editor** open on top of the **Styles** pane with the **Font Family** selector highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="3c542-133">[フォント **ファミリ] ドロップダウンを** 使用して、フォントの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="3c542-133">Use the **Font Family** dropdown to choose from a list of fonts.</span></span>  <span data-ttu-id="3c542-134">フォントは 4 つのグループに分けられます。</span><span class="sxs-lookup"><span data-stu-id="3c542-134">Fonts are organized into four groups.</span></span>  

1.  <span data-ttu-id="3c542-135">計算されたフォント。[スタイル] ウィンドウのスタイルシートで使用できる **フォント** です。</span><span class="sxs-lookup"><span data-stu-id="3c542-135">Computed fonts, which are the fonts available in the stylesheet in the **Styles** pane.</span></span>  
1.  <span data-ttu-id="3c542-136">システム フォント。現在のオペレーティング システムで使用可能なフォントです。</span><span class="sxs-lookup"><span data-stu-id="3c542-136">System fonts, which are the fonts that are available on the current operating system.</span></span>  
1.  <span data-ttu-id="3c542-137">汎用フォント ファミリ (または `serif` `sans-serif` .</span><span class="sxs-lookup"><span data-stu-id="3c542-137">Generic font families, such as `serif` or `sans-serif`.</span></span>  
1.  <span data-ttu-id="3c542-138">Global values, such as `inherit` , `initial` , and `unset` .</span><span class="sxs-lookup"><span data-stu-id="3c542-138">Global values, such as `inherit`, `initial`, and `unset`.</span></span>  
    
:::image type="complex" source="../media/font-editor-font-family-list.msft.png" alt-text="[スタイル] ウィンドウの上部でフォント エディターが開き、フォント ファミリ セレクターが強調表示されている" lightbox="../media/font-editor-font-family-list.msft.png":::
   <span data-ttu-id="3c542-140">[ **スタイル] ウィンドウの** 上部でフォント エディター **が開** き、フォント ファミリ **セレクターが** 強調表示されている</span><span class="sxs-lookup"><span data-stu-id="3c542-140">The **Font Editor** open on top of the **Styles** pane with the **Font Family** selector highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="3c542-141">フォントを選択すると、フォールバック フォントを選択するために別のドロップダウン メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-141">After you choose a font, another dropdown menu is displayed for you to choose fallback fonts.</span></span>  <span data-ttu-id="3c542-142">最大 8 つのフォールバック フォントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3c542-142">You may choose up to eight fallback fonts.</span></span>  <span data-ttu-id="3c542-143">フォントを削除するには、[フォント ファミリの削除 **] アイコンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3c542-143">To remove a font, choose the **Delete Font Family** icon.</span></span>  

<!--:::image type="complex" source="../media/font-editor-defining-fonts.msft.png" alt-text="The font editor with a defined list of fonts and fallback fonts" lightbox="../media/font-editor-defining-fonts.msft.png":::
   The **Font Editor** with a defined list of fonts and fallback fonts highlighted
:::image-end:::  -->

> [!NOTE]
> <span data-ttu-id="3c542-144">フォント ファミリのグローバル値を選択した場合、CSS にはフォールバックが設定されていないので、別のドロップダウンは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3c542-144">If you choose a global value for font family, you do not get another dropdown since there is no fallback for it in CSS.</span></span>  

## <span data-ttu-id="3c542-145">CSS プロパティ エディター</span><span class="sxs-lookup"><span data-stu-id="3c542-145">The CSS Properties editor</span></span>  

<span data-ttu-id="3c542-146">CSS フォントのプロパティは、ビジュアル フォント エディターの下部で **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="3c542-146">You may change CSS font properties in the lower part of the visual **Font Editor**.</span></span>  <span data-ttu-id="3c542-147">UI コントロールを使用して、フォント サイズ、行の高さ、フォントの太さ、文字の間隔を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3c542-147">You may change the font size, line height, font weight, and letter spacing using any of the UI controls.</span></span>  <span data-ttu-id="3c542-148">変更内容はブラウザーで直ちに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-148">Your changes are applied immediately in the browser.</span></span>  

:::image type="complex" source="../media/font-editor-css-properties.msft.png" alt-text="CSS プロパティが強調表示された [スタイル] ウィンドウの上部にフォント エディターが開きます。" lightbox="../media/font-editor-css-properties.msft.png":::
   <span data-ttu-id="3c542-150">[ **スタイル] ウィンドウの** 上部でフォント エディター **が開** き、CSS プロパティが強調表示されている</span><span class="sxs-lookup"><span data-stu-id="3c542-150">The **Font Editor** open on top of the **Styles** pane with the CSS properties highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="3c542-151">また、ビジュアル フォント エディターを使用して CSS 単位を **変換することもできます**。</span><span class="sxs-lookup"><span data-stu-id="3c542-151">You may also convert CSS units using the visual **Font Editor**.</span></span>  <span data-ttu-id="3c542-152">たとえば、[フォント サイズ] スライダーが最初に設定されている\*\*\*\* CSS ルールでこのツールを使用できます `16 pixels` 。</span><span class="sxs-lookup"><span data-stu-id="3c542-152">For example, you may use the tool on a CSS rule where the **Font Size** slider is initially set to `16 pixels`.</span></span>  <span data-ttu-id="3c542-153">ここで、unit ドロップダウンを使用して、値を選択します `em` 。</span><span class="sxs-lookup"><span data-stu-id="3c542-153">Now, use the unit dropdown and choose the value `em`.</span></span>  <span data-ttu-id="3c542-154">表示 `1 em` される値は次の値です `16 pixels` 。</span><span class="sxs-lookup"><span data-stu-id="3c542-154">The `1 em` displayed is equal to `16 pixels`.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-setting-to-16px.msft.png" alt-text="フォント サイズを 16 ピクセルに変更する" lightbox="../media/font-editor-setting-to-16px.msft.png":::
         <span data-ttu-id="3c542-156">フォント サイズを次の値に変更します。</span><span class="sxs-lookup"><span data-stu-id="3c542-156">Change the font size to</span></span> `16 pixels`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-converted-to-em.msft.png" alt-text="unit ドロップダウンを開き、em に変換する" lightbox="../media/font-editor-converted-to-em.msft.png":::
         <span data-ttu-id="3c542-158">変換する単位ドロップダウンを開く</span><span class="sxs-lookup"><span data-stu-id="3c542-158">Open the unit dropdown to convert to</span></span> `em`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3c542-159">Unit ドロップダウンには、使用可能なすべての数値 CSS ユニットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3c542-159">The unit dropdown provides all the numeric CSS units that are available.</span></span>  <span data-ttu-id="3c542-160">フォント サイズ、行の高さ、フォントの太さ、および間隔はすべて異なる単位で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-160">Font size, line height, font weight, and spacing all use different units.</span></span>  <span data-ttu-id="3c542-161">テキスト ボックスにフォーカスがある場合は、キーとキーを選択して設定 `arrow up` `arrow down` を微調整できます。</span><span class="sxs-lookup"><span data-stu-id="3c542-161">When the text boxes have focus, you may select the `arrow up` and `arrow down` keys to fine-tune your settings.</span></span>  <span data-ttu-id="3c542-162">キーボードでスライダーを使う場合は、キーとキー `arrow left` を選択 `arrow down` します。</span><span class="sxs-lookup"><span data-stu-id="3c542-162">To use the sliders with a keyboard, select the `arrow left` and `arrow down` keys.</span></span>  

<span data-ttu-id="3c542-163">CSS プロパティ エディターには、事前設定されたキーワードも含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c542-163">The CSS Properties editor also includes preset keywords.</span></span>  <span data-ttu-id="3c542-164">あらかじめ設定されているキーワードを使う場合は、右側にあるアイコンを選択 `Toggle Input Type` します。</span><span class="sxs-lookup"><span data-stu-id="3c542-164">To use the preset keywords, on the right-hand side, choose the `Toggle Input Type` icon.</span></span>  <span data-ttu-id="3c542-165">UI が変更され、プリセット キーワードのドロップダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c542-165">The UI changes, and a dropdown of preset keywords are displayed.</span></span>  <span data-ttu-id="3c542-166">スライダーや他の UI コントロールを使って UI に戻る場合は、もう一度アイコンを `Toggle Input Type` 選択します。</span><span class="sxs-lookup"><span data-stu-id="3c542-166">To return to the UI with the slider and other UI controls, choose the `Toggle Input Type` icon again.</span></span>  

:::image type="complex" source="../media/font-editor-preset-font-sizes.msft.png" alt-text="事前設定されたキーワード インターフェイスを開く" lightbox="../media/font-editor-preset-font-sizes.msft.png":::
   <span data-ttu-id="3c542-168">事前設定されたキーワード インターフェイスを開く</span><span class="sxs-lookup"><span data-stu-id="3c542-168">Open the preset keyword interface</span></span>  
:::image-end:::  

## <span data-ttu-id="3c542-169">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="3c542-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndex]: ../experimental-features/index.md "試験的な機能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../experimental-features/index.md#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
