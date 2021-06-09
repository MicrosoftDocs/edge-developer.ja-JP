---
description: '[アクセシビリティ] タブを使用してアクセシビリティをテストします。'
title: '[アクセシビリティ] タブを使用してアクセシビリティをテストする'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 839feed56fc82af2b4d96a081c476696166075b9
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597564"
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
# <a name="test-accessibility-using-the-accessibility-tab"></a>[アクセシビリティ] タブを使用してアクセシビリティをテストする

[ **アクセシビリティ] タブ** では、DOM ノードのアクセシビリティ ツリー、ARIA 属性、および計算されたアクセシビリティ プロパティを表示します。  

[アクセシビリティ] **タブを開く** 方法:

1.  [要素] **ツールを** 選択します。  
1.  DOM ツリー **で、** 検査する要素を選択します。  
1.  [アクセシビリティ **] タブを選択** します。 [スタイル] タブの右側 **にある** [その他のタブ] \( [その他のタブ] ボタン \) ボタンを最初 ![ に選択 ](../media/more-tabs-icon.msft.png) する **必要がある場合** があります。

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="[アクセシビリティ] タブで DevTools ホームページの h1 要素を調す" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   [アクセシビリティ `h1` ] タブで DevTools ホームページの **要素を調** す
:::image-end:::  


## <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a>アクセシビリティ ツリーで要素の位置を表示する

アクセシビリティ [ツリーは、DOM][MDNAccessibilityTree] ツリーのサブセットです。  アクセシビリティ ツリーには、スクリーン リーダーなどの支援テクノロジを使用してページのコンテンツを表示する場合に役立つ DOM ツリーの要素だけが含まれます。

アクセシビリティ ツリー内の要素の位置を [アクセシビリティ] タブ **から調** えます。  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="[アクセシビリティ ツリー] セクション" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   [ **アクセシビリティ ツリー]** セクション  
:::image-end:::  


## <a name="view-the-aria-attributes-of-an-element"></a>要素の ARIA 属性を表示する  

ARIA 属性を使用すると、スクリーン リーダーなどの支援テクノロジには、ページの内容を適切に表現するために必要なすべての情報が含まれます。  

[アクセシビリティ] タブで要素の ARIA 属性 **を表示** します。

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="[ARIA 属性] セクション" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   **[ARIA 属性]** セクション  
:::image-end:::  


## <a name="view-the-computed-accessibility-properties-of-an-element"></a>要素の計算されたアクセシビリティ プロパティを表示する  


一部のアクセシビリティ プロパティは、ブラウザーによって動的に計算されます。  これらのプロパティは、[アクセシビリティ] タブ **の [計算されたプロパティ** ] **セクションに表示** されます。  

[アクセシビリティ] タブで、要素の計算されたアクセシビリティ プロパティ **を表示** します。

> [!NOTE]
> 計算された CSS プロパティの場合は、[計算] [タブを使用][DevtoolsCssReferenceViewActuallyAppliedElements] します。

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="[アクセシビリティ] タブの [計算されたプロパティ] セクション" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   [ **アクセシビリティ] タブの** [計算された **プロパティ]** セクション  
:::image-end:::  


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  


<!-- links -->
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "要素に実際に適用される CSS のみを表示する - CSS リファレンス |Microsoft Docs"  
[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "アクセシビリティ ツリー (AOM) |MDN"  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
