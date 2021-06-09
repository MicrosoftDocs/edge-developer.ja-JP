---
description: Color Picker を使用してテキストと色のコントラストをテストします。
title: カラー ピッカーを使用してテキストと色のコントラストをテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f4ba5f3706460c443ae06a393e5ef63e5d336229
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597560"
---
<!-- this article was created on 05/11/2021 by moving a section out from the "Accessibility reference" article (reference.md) -->
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="test-text-color-contrast-using-the-color-picker"></a><span data-ttu-id="92d8a-104">カラー ピッカーを使用してテキストと色のコントラストをテストする</span><span class="sxs-lookup"><span data-stu-id="92d8a-104">Test text-color contrast using the Color Picker</span></span>

<span data-ttu-id="92d8a-105">視力の低い人は、非常に明るい領域や非常に暗い領域を見ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="92d8a-105">People with low vision may not see areas that are very bright or very dark.</span></span>  <span data-ttu-id="92d8a-106">すべてが同じレベルの明るさで表示される傾向があります。これにより、アウトラインとエッジを区別するのは難しくなる。</span><span class="sxs-lookup"><span data-stu-id="92d8a-106">Everything tends to appear at about the same level of brightness, which makes it hard to distinguish outlines and edges.</span></span>  

<span data-ttu-id="92d8a-107">コントラスト比は、テキストの前景と背景の明るさの差を測定します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-107">Contrast ratio measures the difference in brightness between the foreground and background of text.</span></span>  <span data-ttu-id="92d8a-108">テキストのコントラスト比が低い場合は、視力の低いユーザーにサイトが空白の画面として表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="92d8a-108">If your text has a low contrast ratio, then people with low vision may experience your site as a blank screen.</span></span>  

<span data-ttu-id="92d8a-109">DevTools では、テキスト要素のコントラスト比を表示する方法の 1 つは、[スタイル] タブの [色選択] を **使用する方法** です。 Color Picker を使用すると、テキストが推奨されるコントラスト比レベルを満たしているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="92d8a-109">In DevTools, one way to view the contrast ratio of a text element is to use the Color Picker, from the **Styles** tab.  The Color Picker helps you verify that your text meets recommended contrast ratio levels.</span></span>

**<span data-ttu-id="92d8a-110">カラー ピッカーを使用してテキストの色のコントラストを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-110">To check the text-color contrast using the Color Picker:</span></span>**

1.  <span data-ttu-id="92d8a-111">DevTools で、[要素] ツール **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-111">In DevTools, select the **Elements** tool.</span></span>  
1.  <span data-ttu-id="92d8a-112">DOM ツリー **で、** 検査するテキスト要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-112">In the **DOM Tree**, select the text element that you want to inspect.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="DOM ツリーで段落を検査する" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       <span data-ttu-id="92d8a-114">DOM ツリーで段落を **検査する**</span><span class="sxs-lookup"><span data-stu-id="92d8a-114">Inspect a paragraph in the **DOM Tree**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="92d8a-115">[スタイル **] タブ** で、要素に適用される **color** プロパティを見つけて、color プロパティの横にある色の四角形を **選択** します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-115">On the **Styles** tab, locate the **color** property that's applied to the element, and then select the color square next to the **color** property.</span></span>
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="要素の color プロパティ" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       <span data-ttu-id="92d8a-117">要素 `color` のプロパティ</span><span class="sxs-lookup"><span data-stu-id="92d8a-117">The `color` property of the element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="92d8a-118">カラー ピ **ッカーの [** コントラスト比] セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-118">Examine the **Contrast Ratio** section of the Color Picker.</span></span>  <span data-ttu-id="92d8a-119">1 つのチェック マークは、要素が最小推奨事項を満 [たしているという意味です][W3CContrastMinimum]。</span><span class="sxs-lookup"><span data-stu-id="92d8a-119">One check mark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span></span>  <span data-ttu-id="92d8a-120">2 つのチェック マークは、強化された推奨事項を満 [たしています][W3CContrastEnhanced]。</span><span class="sxs-lookup"><span data-stu-id="92d8a-120">Two check marks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="カラー ピッカーの [コントラスト比] セクションには、2 つのチェック マークと 13.97 の値が表示されます。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       <span data-ttu-id="92d8a-122">カラー **ピッカーの [** コントラスト比] セクションには、2 つのチェック マークと値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="92d8a-122">The **Contrast Ratio** section of the Color Picker shows 2 check marks and a value of</span></span> `13.97`  
    :::image-end:::  
    
1.  <span data-ttu-id="92d8a-123">詳細については、[コントラスト比] **セクションを選択して** 展開します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-123">For more information, select the **Contrast ratio** section to expand it.</span></span>  <span data-ttu-id="92d8a-124">カラー ピッカーの上部にあるビジュアル ピッカーには、2 つの線が表示され、現在の色の円と共に、ビジュアル ピッカーを横切って実行されます。</span><span class="sxs-lookup"><span data-stu-id="92d8a-124">In the visual picker at the top of the Color Picker, two lines appear, running across the visual picker, along with a circle for the current color.</span></span>  <span data-ttu-id="92d8a-125">現在の色が推奨事項を満たす場合、行の同じ側にあるものも推奨事項を満たします。</span><span class="sxs-lookup"><span data-stu-id="92d8a-125">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span></span>  <span data-ttu-id="92d8a-126">現在の色が推奨事項を満たしていない場合、同じ側にあるものも推奨事項を満たしません。</span><span class="sxs-lookup"><span data-stu-id="92d8a-126">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span></span>  

    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="ビジュアル ピッカーのコントラスト比線" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       <span data-ttu-id="92d8a-128">ビジュアル **ピッカーの** コントラスト比線</span><span class="sxs-lookup"><span data-stu-id="92d8a-128">The **Contrast Ratio** Line in the visual picker</span></span>  
    :::image-end:::  

1. <span data-ttu-id="92d8a-129">異なる色を試す場合は、ビジュアル ピッカー内で選択するか、カラー ピッカーの下部にある色見本を選択します。</span><span class="sxs-lookup"><span data-stu-id="92d8a-129">To try different colors, select within the visual picker, or select a color swatch at the bottom of the Color Picker.</span></span>
    

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="92d8a-130">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="92d8a-130">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> <span data-ttu-id="92d8a-131">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="92d8a-131">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="92d8a-132">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="92d8a-132">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="92d8a-134">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="92d8a-134">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- links -->  
[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "コントラスト (拡張) レベル AAA |W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "コントラスト (最小) レベル AA |W3C"  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
