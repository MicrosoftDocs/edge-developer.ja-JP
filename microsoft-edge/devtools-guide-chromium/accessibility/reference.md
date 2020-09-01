---
title: アクセシビリティリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 190890b43cff97ae0f379426b68a688534ebda95
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983663"
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





# アクセシビリティリファレンス   



このページでは、Microsoft Edge DevTools のアクセシビリティ機能の包括的な参照を示します。  これは、次のような web 開発者を対象としています。  

*   アプリを開く方法など、DevTools の基本を理解している。  
*   [アクセシビリティの原則とベストプラクティス][MDNAccessibility]について理解している。  
    
このリファレンスの目的は、ページのアクセシビリティを確認するのに役立つ DevTools で利用可能なすべてのツールを見つけるのに役立ちます。  

スクリーンリーダーなどの支援技術を利用して DevTools を操作する方法については、「 [Microsoft Edge DevTools を支援技術でナビゲート][DevtoolsAccessibilityNavigation] する」を参照してください。  

## Microsoft Edge DevTools のアクセシビリティ機能の概要   

このセクションでは、DevTools が全体的なアクセシビリティツールキットにどのように適合するかについて説明します。  

ページにアクセスできるかどうかを判断する際には、次の2つの一般的な質問に留意する必要があります。  

1.  キーボードまたは [スクリーンリーダー][MDNScreenReader]を使用してページ内を移動することはできますか?  
1.  ページの要素は、スクリーンリーダー用に適切にマークされていますか。  
    
一般的に、DevTools は、#2 質問に関連するエラーを解決するのに役立ちます。これらのエラーは、自動的な方法で簡単に検出することができます。  質問 #1 は重要ですが、残念ながら、このツールを使用することはできません。  #1 質問に関連するエラーを見つけるには、自分でキーボードまたはスクリーンリーダーを使用してページを使用する方法しかありません。  <!--See [How To Do An Accessibility Review][AccessibilityReview] to learn more.  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## ページのアクセシビリティを監査する   

> [!NOTE]
> **監査**パネルは、サードパーティの web サイトでホストされているコンテンツへのリンクを提供します。  Microsoft は、これらのサイトのコンテンツおよび収集される可能性のあるデータを管理する責任を負いません。  

一般的に、監査パネルを使用して、次のことを確認します。  

*   ページには、スクリーンリーダーのマークが正しく設定されています。  
*   ページ上のテキスト要素には、十分なコントラスト率があります。 「 [カラーピッカーのテキスト要素のコントラスト比](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)を確認する」もご覧ください。  
    
ページを監査するには、次の操作を行います。  

1.  監査する URL に移動します。  
1.  DevTools で、[ **監査** ] タブをクリックします。 DevTools には、さまざまな構成オプションが表示されます。  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="監査を構成する" lightbox="../media/accessibility-audits-pane.msft.png":::
       監査を構成する  
    :::image-end:::  
    
    > [!NOTE]
    > このセクションのスクリーンショットは、Microsoft Edge のバージョン79で採用されています。  実行しているバージョンを確認でき `edge://version` ます。  **監査**パネルの UI は、以前のバージョンの Microsoft Edge では異なりますが、一般的なワークフローは同じです。  
    
1.  モバイルデバイスをシミュレートする場合は、[ **デバイス**] で [ **モバイル** ] を選択します。  このオプションでは、ユーザーエージェントの文字列が変更され、ビューポートのサイズが変更されます。  ページのモバイルバージョンの表示がデスクトップバージョンとは異なる場合、このオプションは監査結果に大きな影響を与える可能性があります。  
1.  [ **監査** ] セクションで、[ **アクセシビリティ** ] が有効になっていることを確認します。  レポートから除外する場合は、その他のカテゴリを無効にします。  ページの品質を向上させるその他の方法を見つける場合は、有効のままにしておきます。  
1.  [ **調整** ] セクションでは、ネットワークと CPU を調整することができます。これは、読み込みのパフォーマンスを分析するときに役立ちます。  このオプションは、お客様のアクセシビリティのスコアには無関係であるため、好きなように使用できます。  
1.  [ **記憶域のクリア** ] チェックボックスを使用すると、ページを読み込む前にすべての記憶域をクリアするか、ページの読み込みの間に記憶域を保持することができます。  このオプションは、アクセシビリティのスコアには無関係であるため、好きなように使用することもできます。  
1.  [ **監査の実行**] をクリックします。 10 ~ 30 秒後に、DevTools でレポートが提供されます。  レポートには、ページのアクセシビリティを向上させるためのさまざまなヒントが用意されています。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="レポート" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       レポート  
    :::image-end:::  
    
1.  詳細については、監査をクリックしてください。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="監査に関するその他の情報" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       監査に関するその他の情報  
    :::image-end:::  
    
1.  [ **詳細情報** ] をクリックして、その監査のドキュメントを表示します。
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="監査のドキュメントを表示する" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       監査のドキュメントを表示する  
    :::image-end:::  
    
### 「アックス extension」もご覧ください。   

**監査**パネルではなく、[アックスの拡張機能][ChromeWebStoreAxe]を使用することをお勧めします。  
通常、アックス extension は、監査パネルを累乗する基になるエンジンであるため、同じ情報を提供します。  アックス extension にはさまざまな UI があり、監査の方法は少し異なります。  
[ **監査** ] パネルに表示される [アックス extension] の利点の1つは、障害のあるノードを検査して強調表示できることです。  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="アックス extension" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   アックス extension  
:::image-end:::  

## [アクセシビリティ] ウィンドウ   

[ **アクセシビリティ** ] ウィンドウは、DOM ノードのアクセシビリティツリー、ARIA 属性、および計算されたアクセシビリティプロパティを表示する場所です。  

[ **アクセシビリティ** ] ウィンドウを開くには:  

1.  [ **要素** ] タブをクリックします。  
1.  **DOM ツリー**で、検査する要素を選択します。  
1.  [ **アクセシビリティ** ] タブをクリックします。 このタブは、[その他 **] タブの** ![ [その他] タブの下に隠れている可能性があり ][ImageMoreTabsIcon] ます。  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="[アクセシビリティ] ウィンドウで DevTools ホームページの h1 要素を検査する" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   [ `h1` **アクセシビリティ** ] ウィンドウで devtools ホームページの要素を検査する  
:::image-end:::  

### アクセシビリティツリーの要素の位置を表示する   

[アクセシビリティツリー][MDNAccessibilityTree]は DOM ツリーのサブセットです。  DOM ツリーの要素のみが含まれます。これには、スクリーンリーダーでページのコンテンツを表示するために役立つ、関連する有用な要素が含まれています。  

アクセシビリティツリーの要素の位置を [ [アクセシビリティ] ウィンドウ](#the-accessibility-pane)から調べます。  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="[アクセシビリティツリー] セクション" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   [ **アクセシビリティツリー** ] セクション  
:::image-end:::  

### 要素の ARIA 属性を表示する   

ARIA 属性によって、ページのコンテンツを適切に表すために必要なすべての情報をスクリーンリーダーに確実に含めることができます。  

[ [アクセシビリティ] ウィンドウ](#the-accessibility-pane)で要素の ARIA 属性を表示します。  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="[ARIA 属性] セクション" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   [ **ARIA 属性** ] セクション  
:::image-end:::  

### 要素の計算されたアクセシビリティプロパティを表示する   

> [!NOTE]
> 計算された CSS プロパティを検索する場合は、[ [計算] タブ][DevtoolsCssReferenceViewActuallyAppliedElements]を参照してください。  

一部のアクセシビリティプロパティは、ブラウザーによって動的に計算されます。  これらのプロパティは、[**アクセシビリティ**] ウィンドウの [計算された**プロパティ**] セクションに表示されます。  

[ [アクセシビリティ] ウィンドウ](#the-accessibility-pane)で、要素の計算されたアクセシビリティプロパティを表示します。  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="[アクセシビリティ] ウィンドウの [計算されたプロパティ] セクション" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   [**アクセシビリティ**] ウィンドウの [計算された**プロパティ**] セクション  
:::image-end:::  

## カラーピッカーでのテキスト要素のコントラスト比の表示   

視覚障碍のあるユーザーは、領域を非常に明るく、または非常に暗くします。  すべての機能が同じ輝度で表示される傾向があります。これにより、アウトラインとエッジを区別しにくくなります。  
コントラスト比は、テキストの前景と背景の間の輝度の差を測定します。  テキストのコントラスト比が低い場合、これらの視覚に障碍があるユーザーは、文字どおり空の画面としてサイトを表示する可能性があります。  

カラーピッカーは、テキストが推奨されるコントラスト比レベルを満たしているかどうかを確認するのに役立ちます。  

1.  [ **要素** ] タブをクリックします。  
1.  **DOM ツリー**で、検査するテキスト要素を選択します。  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="DOM ツリーの段落の検査" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       DOM ツリーの段落の検査  
    :::image-end:::  
    
1.  [ **スタイル** ] ウィンドウで、要素の値の横にある色の四角をクリックし `color` ます。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="要素の color プロパティ" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       `color`要素のプロパティ  
    :::image-end:::  
    
1.  カラーピッカーの [ **コントラスト比** ] のチェックボックスをオンにします。  1つのチェックマークは、要素が [最小要件][W3CContrastMinimum]を満たしていることを意味します。  2つのチェックマークは、強化された [推奨事項][W3CContrastEnhanced]を満たしていることを意味します。
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="カラーピッカーの [コントラスト比] セクションには、2つのチェックマークと値13.97 が表示されます。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       カラーピッカーの [ **コントラスト比** ] セクションには、2つのチェックマークと値が表示されます。 `13.97`  
    :::image-end:::  
    
1.  [ **コントラスト比** ] セクションをクリックして、詳細情報を表示します。  カラーピッカーの上部にあるビジュアルピッカーに線が表示されます。  現在の色が推奨事項を満たしている場合は、その行の同じ側にあるものも、推奨事項を満たしているものとします。  現在の色が推奨事項を満たしていない場合は、同じ側にあるものも、推奨されません。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="ビジュアルピッカーのコントラスト比線" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       ビジュアルピッカーのコントラスト比線  
    :::image-end:::  
    
<!--## Feedback   -->  



<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "支援技術を使用して Microsoft Edge DevTools を操作する |Microsft のドキュメント"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "要素の CSS 参照に実際に適用されている CSS のみを表示します。 |Microsoft ドキュメント"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "アックス-Web アクセシビリティテスト-Chrome Web ストア"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "アクセシビリティツリー (AOM) |MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "アクセシビリティ |MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "スクリーンリーダー |MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "コントラスト (強化) レベル AAA |勧告"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "コントラスト (最小) レベル AA |勧告"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
