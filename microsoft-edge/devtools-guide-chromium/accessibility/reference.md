---
description: DevTools のアクセシビリティ機能のMicrosoft Edge参照。
title: アクセシビリティリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a82dec6ffd7e3fb44143ea103fc9756afcd1a161
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564575"
---
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
# <a name="accessibility-reference"></a>アクセシビリティリファレンス  

このページは、DevTools のアクセシビリティ機能のMicrosoft Edgeです。  これは、次の Web 開発者を対象とします。  

*   DevTools を開く方法など、基本的な理解を深める必要があります。  
*   アクセシビリティの原則 [とベスト プラクティスに精通しています][MDNAccessibility]。  
    
この参照の目的は、ページのアクセシビリティを調べるのに役立つ DevTools で利用可能なすべてのツールを見つけるために役立ちます。  

スクリーン リーダーのような支援テクノロジを使用して DevTools をナビゲートする際のヘルプを探している場合は、「Navigateing Microsoft Edge [DevTools][DevtoolsAccessibilityNavigation]with Assistive Technology 」に移動します。  

## <a name="overview-of-accessibility-features-in-microsoft-edge-devtools"></a>DevTools のアクセシビリティ機能Microsoft Edge概要  

このセクションでは、DevTools がアクセシビリティ ツールキット全体に適合する方法について説明します。  

ページにアクセスできるかどうかを判断するには、次の 2 つの一般的な質問を念頭に置く必要があります。  

1.  キーボードまたはスクリーン リーダーでページを [移動できますか][MDNScreenReader]。  
1.  ページの要素がスクリーン リーダー用に適切にマークされていますか?  
    
一般に、DevTools は、これらのエラーを自動的に検出しやすいため、質問#2に関連するエラーを修正するのに役立ちます。  質問#1同様に重要ですが、残念ながら DevTools はそこで役立つとは限らない。  質問に関連するエラーを見つける#1、キーボードまたはスクリーン リーダーを使用してページを使用してみてください。  <!--To learn more, navigate to [How To Do An Accessibility Review][AccessibilityReview].  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <a name="audit-the-accessibility-of-a-page"></a>ページのアクセシビリティを監査する  

> [!NOTE]
> 監査 **ツールは、** サードパーティの Web サイトでホストされているコンテンツへのリンクを提供します。  Microsoft は、これらのサイトのコンテンツおよび収集される可能性があるデータについて責任を負いません。  

一般に、[監査] パネルを使用して、次の条件を確認します。  

*   ページがスクリーン リーダー用に適切にマークされています。  
*   ページ上のテキスト要素には十分なコントラスト比があります。  [カラー [ピッカー] でテキスト要素のコントラスト比を表示するに移動します](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)。  

ページを監査するには、次の方法を実行します。  

1.  監査する URL に移動します。  
1.  DevTools で、[監査] **ツールを選択** します。  DevTools には、さまざまな構成オプションが表示されます。  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="監査の構成" lightbox="../media/accessibility-audits-pane.msft.png":::
       監査の構成  
    :::image-end:::  
    
    > [!NOTE]
    > このセクションのスクリーンショットは、バージョン 79 でMicrosoft Edgeされました。  実行しているバージョンを確認できます `edge://version` 。  監査**ツール**の UI は、以前のバージョンのワークフローではMicrosoft Edge異なって見えますが、一般的なワークフローは同じです。  
    
1.  [ **デバイス]** で、 **モバイル** デバイスをシミュレートする場合は[モバイル] を選択します。  このオプションは、ユーザー エージェントの文字列を変更し、ビューポートのサイズを変更します。  モバイル バージョンのページがデスクトップ バージョンとは異なる場合、このオプションは監査の結果に大きな影響を与える可能性があります。  
1.  [監査 **] セクション** で、アクセシビリティが **有効になっているか** 確認します。  レポートから除外する場合は、他のカテゴリを無効にします。  ページの品質を向上させる他の方法を見つけしたい場合は、有効のままにします。  
1.  [ **調整] セクション** では、負荷のパフォーマンスを分析するときに役立つネットワークと CPU を調整できます。  このオプションはアクセシビリティ スコアとは無関係である必要があります。そのため、必要に応じて使用できます。  
1.  [**ページのStorage]** チェック ボックスをオンにすると、ページを読み込む前にすべての記憶域をクリアしたり、ページ読み込みの間にストレージを保持することができます。  このオプションは、アクセシビリティ スコアとは無関係な場合も考え、必要に応じて使用できます。  
1.  [ **監査の実行] を選択します**。 10 ~ 30 秒後、DevTools はレポートを提供します。  レポートには、ページのアクセシビリティを向上させる方法に関するさまざまなヒントが示されています。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="レポート" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       レポート  
    :::image-end:::  
    
1.  監査を選択して、詳細を確認します。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="監査の詳細" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       監査の詳細  
    :::image-end:::  
    
1.  [ **詳細] を選択** して、その監査のドキュメントを表示します。  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="監査のドキュメントを表示する" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       監査のドキュメントを表示する  
    :::image-end:::  
    
### <a name="see-also-axe-extension"></a>「aXe extension」も参照  

監査ツールではなく [、aXe][ChromeWebStoreAxe] 拡張機能を **使用する方が良** い場合があります。  
aXe 拡張機能は、通常、Audits パネルに電力を供給する基になるエンジンであるので、同じ情報を提供します。  aXe 拡張機能の UI は異なります。監査の説明は若干異なります。  
aXe 拡張機能が **Audits** ツールを超える利点の 1 つは、障害が発生したノードを検査して強調表示できる点です。  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="aXe 拡張機能" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   aXe 拡張機能  
:::image-end:::  

## <a name="the-accessibility-panel"></a>[アクセシビリティ] パネル  

アクセシビリティ **パネルは** 、DOM ノードのアクセシビリティ ツリー、ARIA 属性、および計算されたアクセシビリティ プロパティを表示する場所です。  

[アクセシビリティ] **パネルを開く** 方法は次の操作を行います。  

1.  [要素] **ツールを選択** します。  
1.  DOM ツリー **で、** 検査する要素を選択します。  
1.  [アクセシビリティ **] パネルを選択** します。  このパネルは、[その他のタブ] \( **More Tabs** \) ボタン ![ の ](../media/more-tabs-icon.msft.png) 背後に非表示になる場合があります。  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="アクセシビリティ パネルで DevTools ホームページの h1 要素を検査する" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   アクセシビリティ パネル `h1` で DevTools ホームページの **要素を検査** する  
:::image-end:::  

### <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a>アクセシビリティ ツリー内の要素の位置を表示する  

アクセシビリティ [ツリーは、DOM][MDNAccessibilityTree] ツリーのサブセットです。  これは、スクリーン リーダーにページの内容を表示するために関連し、有用な DOM ツリーの要素のみを含む。  

アクセシビリティ パネルからアクセシビリティ ツリー内の要素の [位置を調](#the-accessibility-panel) えます。  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="[アクセシビリティ ツリー] セクション" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   [ **アクセシビリティ ツリー]** セクション  
:::image-end:::  

### <a name="view-the-aria-attributes-of-an-element"></a>要素の ARIA 属性を表示する  

ARIA 属性を使用すると、ページの内容を適切に表現するために必要なすべての情報がスクリーン リーダーに提供されます。  

アクセシビリティ パネルで要素の ARIA 属性 [を表示](#the-accessibility-panel) します。  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="[ARIA 属性] セクション" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   **[ARIA 属性]** セクション  
:::image-end:::  

### <a name="view-the-computed-accessibility-properties-of-an-element"></a>要素の計算されたアクセシビリティ プロパティを表示する  

> [!NOTE]
> 計算された CSS プロパティを探している場合は、[計算] [パネルに移動][DevtoolsCssReferenceViewActuallyAppliedElements] します。  

一部のアクセシビリティ プロパティは、ブラウザーによって動的に計算されます。  これらのプロパティは、[アクセシビリティ] パネル **の [計算されたプロパティ** ] **セクションに表示** されます。  

[アクセシビリティ] パネルで、要素の計算されたアクセシビリティ プロパティ [を表示](#the-accessibility-panel) します。  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="[アクセシビリティ] パネルの [計算されたプロパティ] セクション" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   [ **アクセシビリティ] パネルの** [ **計算されたプロパティ]** セクション  
:::image-end:::  

## <a name="view-the-contrast-ratio-of-a-text-element-in-the-color-picker"></a>Color Picker でテキスト要素のコントラスト比を表示する  

視力の低い人の中には、領域が非常に明るい、または非常に暗いと見なされない人もいます。  すべてが同じ明るさで表示される傾向があります。これにより、アウトラインとエッジを区別するのは難しくなる。  

コントラスト比は、テキストの前景と背景の明るさの差を測定します。  テキストのコントラスト比が低い場合、これらの低ビジョン ユーザーは文字通りサイトを空白の画面として表示する場合があります。  

カラー ピッカーを使用すると、テキストが推奨されるコントラスト比レベルを満たしているのを確認できます。  

1.  [要素] **ツールを選択** します。  
1.  DOM ツリー **で、** 検査するテキスト要素を選択します。  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="DOM ツリーで段落を検査する" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       DOM ツリーで段落を **検査する**  
    :::image-end:::  
    
1.  [スタイル **] パネル** で、要素の値の横にある `color` 色の四角形を選択します。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="要素の color プロパティ" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       要素 `color` のプロパティ  
    :::image-end:::  
    
1.  カラー ピ **ッカーの [** コントラスト比] セクションを確認します。  1 つのチェックマークは、要素が最小推奨事項を満 [たしているという意味です][W3CContrastMinimum]。  2 つのチェック マークは、強化された推奨事項を満 [たしています][W3CContrastEnhanced]。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="カラー ピッカーの [コントラスト比] セクションには、2 つのチェックマークと 13.97 の値が表示されます。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       カラー **ピッカーの** [コントラスト比] セクションには、2 つのチェックマークと値が表示されます。 `13.97`  
    :::image-end:::  
    
1.  詳細については、[コントラスト比] **セクションを選択** します。  カラー ピッカーの上部にあるビジュアル ピッカーに線が表示されます。  現在の色が推奨事項を満たす場合、行の同じ側にあるものも推奨事項を満たします。  現在の色が推奨事項を満たしていない場合、同じ側にあるものも推奨事項を満たしません。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="ビジュアル ピッカーのコントラスト比線" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       ビジュアル **ピッカーの** コントラスト比線  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "支援Microsoft Edgeを使用して DevTools を操作|Microsoft Docs"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "要素に実際に適用される CSS のみを表示する - CSS リファレンス |Microsoft Docs"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe - Web アクセシビリティ テスト - Chrome ウェブストア"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "アクセシビリティ ツリー (AOM) |MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "アクセシビリティ |MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "スクリーン リーダー |MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "コントラスト (拡張) レベル AAA |W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "コントラスト (最小) レベル AA |W3C"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
