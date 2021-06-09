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
# <a name="test-text-color-contrast-using-the-color-picker"></a>カラー ピッカーを使用してテキストと色のコントラストをテストする

視力の低い人は、非常に明るい領域や非常に暗い領域を見ない場合があります。  すべてが同じレベルの明るさで表示される傾向があります。これにより、アウトラインとエッジを区別するのは難しくなる。  

コントラスト比は、テキストの前景と背景の明るさの差を測定します。  テキストのコントラスト比が低い場合は、視力の低いユーザーにサイトが空白の画面として表示される場合があります。  

DevTools では、テキスト要素のコントラスト比を表示する方法の 1 つは、[スタイル] タブの [色選択] を **使用する方法** です。 Color Picker を使用すると、テキストが推奨されるコントラスト比レベルを満たしているのを確認できます。

**カラー ピッカーを使用してテキストの色のコントラストを確認するには、次のコマンドを実行します。**

1.  DevTools で、[要素] ツール **を選択** します。  
1.  DOM ツリー **で、** 検査するテキスト要素を選択します。  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="DOM ツリーで段落を検査する" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       DOM ツリーで段落を **検査する**  
    :::image-end:::  
    
1.  [スタイル **] タブ** で、要素に適用される **color** プロパティを見つけて、color プロパティの横にある色の四角形を **選択** します。
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="要素の color プロパティ" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       要素 `color` のプロパティ  
    :::image-end:::  
    
1.  カラー ピ **ッカーの [** コントラスト比] セクションを確認します。  1 つのチェック マークは、要素が最小推奨事項を満 [たしているという意味です][W3CContrastMinimum]。  2 つのチェック マークは、強化された推奨事項を満 [たしています][W3CContrastEnhanced]。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="カラー ピッカーの [コントラスト比] セクションには、2 つのチェック マークと 13.97 の値が表示されます。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       カラー **ピッカーの [** コントラスト比] セクションには、2 つのチェック マークと値が表示されます。 `13.97`  
    :::image-end:::  
    
1.  詳細については、[コントラスト比] **セクションを選択して** 展開します。  カラー ピッカーの上部にあるビジュアル ピッカーには、2 つの線が表示され、現在の色の円と共に、ビジュアル ピッカーを横切って実行されます。  現在の色が推奨事項を満たす場合、行の同じ側にあるものも推奨事項を満たします。  現在の色が推奨事項を満たしていない場合、同じ側にあるものも推奨事項を満たしません。  

    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="ビジュアル ピッカーのコントラスト比線" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       ビジュアル **ピッカーの** コントラスト比線  
    :::image-end:::  

1. 異なる色を試す場合は、ビジュアル ピッカー内で選択するか、カラー ピッカーの下部にある色見本を選択します。
    

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  


<!-- links -->  
[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "コントラスト (拡張) レベル AAA |W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "コントラスト (最小) レベル AA |W3C"  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
