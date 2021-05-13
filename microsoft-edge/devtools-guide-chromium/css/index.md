---
description: DevTools を使用Microsoft Edgeページの CSS を表示および変更する方法について説明します。
title: CSS の表示と変更の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bc629286530e709bef0e04a671f1a0e56eee48ea
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564449"
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
# <a name="get-started-with-viewing-and-changing-css"></a>CSS の表示と変更の概要  

これらの対話型チュートリアルを完了して、DevTools を使用してページの CSS を表示および変更するMicrosoft Edgeします。  

## <a name="open-css-examples"></a>オープン CSS の例  

1.  `Control`\(Windows、Linux\) または `Command` \(macOS\) を保持し **、[CSS の**例] を選択して新しいウィンドウを開きます。  
    
    [CSS の例][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > DevTools ウィンドウをビューポート \(次の図\に表示)の右側にドッキングする場合は [、[DevTools][DevToolsCustomizePlacement] のカスタマイズと制御] を **選択します** `...` 。  **[DevTools のカスタマイズ**と制御] ドロップダウン メニューの [**ドック**側] セクションで、[右へドック]**を選択します**。  
    
## <a name="view-the-css-for-an-element"></a>要素の CSS を表示する  

1.  [CSS の例を開きます](#open-css-examples)。  
1.  テキストにカーソルを `Inspect Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
    1.  DevTools の [ **要素** ] ツールの **[DOM ツリー** ] パネルで、要素 `Inspect Me!` が強調表示されます。  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="検査された要素が DOM ツリーで強調表示されている" lightbox="../media/css-elements-inspect-me.msft.png":::
           検査された要素が DOM ツリーで **強調表示されている**  
        :::image-end:::  
        
    1.  要素で `Inspect Me!` 、属性の値を見つけて `data-message` コピーします。  
1.  ページの [値:] **テキスト `data-message` ** ボックスに値を入力します。  
1.  テキストにカーソルを `Inspect Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
    1.  DevTools の [要素] **ツールで** 、[スタイル] パネル **を選択** します。  
    1.  [スタイル **] パネル** で、 `Inspect Me!` 要素が強調表示されます。  
    1.  要素で `Inspect Me!` 、クラス ルール `aloha` を検索します。  
        
        > [!NOTE]
        > このルールは、要素に適用されるので表示 `Inspect Me!` されます。  
        
    1.  クラスで `aloha` 、スタイルの値を見つけて `padding` コピーします。  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="CSS クラスが検査済み要素に適用される場合は、[スタイル] パネルで強調表示されます。" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           CSS クラスは、[スタイル] パネルに表示されるなど、選択 `aloha` した要素に **適用** されます。  
        :::image-end:::  
        
1.  ページの [値:] **テキスト `padding` ** ボックスに値を入力します。  

## <a name="add-a-css-declaration-to-an-element"></a>要素に CSS 宣言を追加する  

CSS 宣言 **を** 要素に変更または追加する場合は、[スタイル] パネルを使用します。  

> [!NOTE]
> この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。  

1.  [CSS の例を開きます](#open-css-examples)。  
1.  テキストにカーソルを `Add A Background Color To Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
1.  [スタイル `element.style` ] パネルの上部付近 **を選択** します。  
1.  `background-color` を入力して、`Enter` を選択します。  
1.  `honeydew` を入力して、`Enter` を選択します。  DOM ツリー **では、** 要素に適用されるインライン スタイル宣言が表示されます。  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="[スタイル] パネルを使用して要素に CSS 宣言を追加する" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       宣言 `background-color:honeydew` は、[スタイル] パネルのセクションを使用 `element.style` して要素に **適用** されます。  
    :::image-end:::  
    
## <a name="add-a-css-class-to-an-element"></a>要素に CSS クラスを追加する  

CSS クラスが要素に適用または要素から削除された場合の要素の外観を表示するには、[スタイル] パネルに **移動** します。  

> [!NOTE]
> この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。  

1.  [CSS の例を開きます](#open-css-examples)。  
1.  テキストにカーソルを `Add A Class To Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
1.  **[.cls] を選択します**。  DevTools は、選択した要素にクラスを追加できるテキスト ボックスを表示します。  
1.  [ `color_me` 新しいクラスの **追加] テキスト ボックスに** 入力し、[] を選択します `Enter` 。  [新しいクラスの追加] **テキスト** ボックスの下にチェック ボックスが表示され、クラスのオンとオフを切り替えます。  要素に `Add A Class To Me!` 他のクラスが適用されている場合は、ここから各クラスを切り替えすることもできます。  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="要素にcolor_meクラスを適用する" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       クラス `color_me` は、[スタイル] パネルの **.cls** セクションを使用して要素に **適用** されます。  
    :::image-end:::  
    
## <a name="add-a-pseudostate-to-a-class"></a>クラスに擬似状態を追加する  

CSS 擬似 **状態を** 要素に完全に適用するには、[スタイル] パネルを使用します。  DevTools `:active` は `:focus` 、、、、 `:hover` および をサポートしています `:visited` 。  

> [!NOTE]
> この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。  

1.  [CSS の例を開きます](#open-css-examples)。  
1.  テキストにカーソルを `Hover Over Me!` 合わせる。  背景色が変更されます。  
1.  テキストにカーソルを `Hover Over Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
1.  [スタイル]**パネルで****、[:hov] を選択します**。  
1.  **[:hover] チェック ボックスを**オンにします。  要素の上に実際にカーソルを置かなくても、背景色は以前と同様に変化します。  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="要素のホバー擬似状態を切り替える" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       要素の `:hover` 擬似状態を切り替える  
    :::image-end:::  
    
## <a name="change-the-dimensions-of-an-element"></a>要素の寸法を変更する  

要素の**幅、高**さ、余白****、余白、または罫線の長さを変更するには、[スタイル] パネルの [ボックス モデル] 対話型図を使用します。  

> [!NOTE]
> この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。  

1.  [CSS の例を開きます](#open-css-examples)。  
1.  テキストにカーソルを `Change My Margin!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
1.  [スタイル **] パネルのボックス** モデル図 **で** 、パディングをポイント **します**。  要素のパディングがビューポートで強調表示されます。  

    > [!NOTE]
    > DevTools ウィンドウのサイズによっては、[スタイル] パネルの下部までスクロールしてボックス モデルを******表示する必要があります**。  

1.  現在、要素に左余白がないという意味の値を持つ Box **Model**の左余白を `-` ダブルクリックします。  
1.  `100px` を入力して、`Enter` を選択します。  Box **Model の** 既定値はピクセルですが、その他の値 (例: 、 、 `25%` など) も受け入れ可能です `10vw` 。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="要素のパディングにカーソルを合わせる" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             要素のパディングにカーソルを合わせる  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="要素の左余白を変更する" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             要素の左余白を変更する  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="debugging-media-queries"></a>メディア クエリのデバッグ  

[メディア クエリは][MDNUsingMediaGueries] 、Web 製品を各ユーザーの構成設定の変更に対応させる方法です。  最も重要な使用例は、ビューポートの寸法に応じて製品に異なる CSS レイアウトを提供する方法です。  個別のレイアウトを使用すると、モバイル デバイス用の 1 列レイアウトと、利用可能な画面管理が多い場合の複数列レイアウトを使用できます。  

CSS で定義したメディア クエリをデバッグまたはテストする場合は、次の手順を使用します。  

1.  開発者ツールを開き、左上**の**2 番目のトグル デバイス ツールバー アイコンを選択するか `Ctrl` + `Shift` + `M` 、macOS\で \( `Cmd` + `Shift` + `M` を選択します)。  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="デバイス ツールバーを開く" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       デバイス ツールバーを開く  
    :::image-end:::  
    
1.  デバイス ツール バーを開いた後、上部右側のメニューを選択し、[メディア `...` クエリの表示 **] を選択します**。  Web ページの上に表示される色付きバーは、さまざまなメディア クエリを表します。  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="デバイス ツールバーにメディア クエリを表示する" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       デバイス ツールバーにメディア クエリを表示する  
    :::image-end:::  
    
1.  バーの境界にカーソルを合わせると、さまざまなメディア クエリの値が表示されます。  一致する Web ページのサイズを変更するには、それぞれを選択します。  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="プレビュー バーからメディア クエリを選択する" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       プレビュー バーからメディア クエリを選択する  
    :::image-end:::  
    
1.  メディア クエリをデバッグし、エディターで CSS ファイルを開く場合は、いずれかのバー セグメントにカーソルを合わせ、コンテキスト メニュー \(右クリック\) を開き `Sources` 、を選択します `reveal in source code` 。  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="ソース エディターでメディア クエリを表示する" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       ソース エディターでメディア クエリを表示する  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "DevTools Microsoft Edgeの配置を変更する (Undock、Dock to Bottom、Dock to Left)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS の例 - Microsoft Edge (Chromium) DevTools |Glitch"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディア クエリの使用|MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
