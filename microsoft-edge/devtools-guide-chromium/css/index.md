---
title: CSS の表示と変更を始める
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 85fceaa44b0143a82ca8f66ef8c63e1a9275dcd8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601818"
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





# CSS の表示と変更を始める   



Microsoft Edge DevTools を使用して、ページの CSS を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。  

## CSS の例を開く  

1.  `Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **CSS の例**] をクリックして新しいウィンドウで開きます。  
    
    [CSS の例][GlitchDevToolsCssExamples]  

> [!NOTE]
> ツールビュー ([図 1](#figure-1)\) の右側に[devtools ウィンドウをドッキング][DevToolsCustomizePlacement]する場合は、[ **devtools のカスタマイズと制御**] をクリックし `...` ます。  [ **DevTools のカスタマイズと制御**] ドロップダウンメニューの [ **dock** ] セクションで、[ **dock to right**] を選びます。  
    
## 要素の CSS を表示する   

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストを右クリック `Inspect Me!` し、[**検査**] を選択します。  
    1.  DevTools の [**要素**] パネルで、[ **DOM Tree** ] タブの `Inspect Me!` 要素が強調表示されています。  
        
        > ##### 図 1  
        > **DOM ツリー**で、検査された要素が強調表示される  
        > ![DOM ツリーで、検査された要素が強調表示される][ImageInspect]  
        
    1.  要素で、 `Inspect Me!` 属性の値を見つけ `data-message` てコピーします。  
1.  ページの [**値] `data-message` :** textbox で、値を入力します。  
1.  テキストを右クリック `Inspect Me!` し、[**検査**] を選択します。  
    
    1.  [DevTools] の [**要素**] パネルで、[**スタイル**] タブを選択します。  
    1.  [**スタイル**] タブに、 `Inspect Me!` 要素が強調表示されています。  
    1.  要素で、 `Inspect Me!` クラスの規則を見つけ `aloha` ます。  
        
        > [!NOTE]
        > この規則は、要素に適用されているために表示され `Inspect Me!` ます。  
        
    1.  クラスで、 `aloha` スタイルの値を見つけ `padding` てコピーします。  
        
        > ##### 図 2  
        > 選択した要素に適用される CSS クラス (など) `aloha` が [**スタイル**] タブに表示されます。  
        > ![[スタイル] タブの [検査] 要素に適用されている CSS クラスが強調表示されている][ImageAloha]  
        
1.  ページの [**値] `padding` :** textbox で、値を入力します。  

## 要素に CSS 宣言を追加する   

要素に CSS 宣言を変更したり追加したりするときは、[**スタイル**] タブを使います。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストを右クリック `Add A Background Color To Me!` し、[**検査**] を選択します。  
1.  [ `element.style` **スタイル**] タブの上部にあるをクリックします。  
1.  入力 `background-color` して、キーを押し `Enter` ます。  
1.  入力 `honeydew` して、キーを押し `Enter` ます。  **DOM ツリー**で、インラインスタイル宣言が要素に適用されていることを確認します。  

> ##### 図 3  
> `background-color:honeydew`宣言は `element.style` 、[**スタイル**] タブのセクションを使って要素に適用されています。  
> ![[スタイル] タブを使用した要素への CSS 宣言の追加][ImageDeclaration]  

## CSS クラスを要素に追加する   

[**スタイル**] タブを使って、要素に対して CSS クラスを適用または削除したときの要素の外観を確認します。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  要素を右クリック `Add A Class To Me!` し、[**検査**] を選択します。  
1.  [ **Cls**] をクリックします。  DevTools は、選択した要素にクラスを追加できるテキストボックスを表示します。  
1.  `color_me`[**新しいクラスの追加**] テキストボックスに入力して、キーを押し `Enter` ます。  [**新しいクラスの追加**] テキストボックスの下に、クラスのオンとオフを切り替えることができるチェックボックスが表示されます。  `Add A Class To Me!`要素に他のクラスが適用されている場合は、それぞれのクラスをここから切り替えることもできます。  

> ##### 図 4  
> この `color_me` クラスは、[**スタイル**] タブの [cls] セクションを使って要素に適用されてい**ます。**  
> ![要素への color_me クラスの適用][ImageApplyClass]  

## 疑似状態をクラスに追加する   

[**スタイル**] タブを使って、CSS の疑似条件を要素に永続的に適用します。  Devtools では、、、、という機能がサポートさ `:active` `:focus` `:hover` れてい `:visited` ます。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストの上にマウスポインターを置き `Hover Over Me!` ます。  背景色が変更されます。  
1.  テキストを右クリック `Hover Over Me!` し、[**検査**] を選択します。  
1.  [**スタイル**] タブで、 **: hov**をクリックします。  
1.  [ **: Hover** ] チェックボックスをオンにします。  実際には、要素の上にマウスポインターを置いていない場合でも背景色は変わります。  

> ##### 図 5  
> `:hover`要素の擬似状態の切り替え  
> ![要素の hover 擬似状態の切り替え][ImageSetHover]  

## 要素のサイズを変更する   

[**スタイル**] タブの**Box モデル**対話型ダイアグラムを使用して、要素の幅、高さ、パディング、余白、または境界線の長さを変更します。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  要素を右クリック `Change My Margin!` し、[**検査**] を選択します。  
1.  **ボックスモデル**図の [**スタイル**] タブで、**パディング**の上にマウスポインターを置きます。  ビューポートで要素のパディングが強調表示されています。  

    > [!NOTE]
    > DevTools ウィンドウのサイズによっては、[**スタイル**] タブの下部にスクロールして、**ボックスモデル**を表示しなければならない場合があります。  

1.  **ボックスモデル**の左余白をダブルクリックします。現在のところ、 `-` 要素には左余白がない意味の値が含まれています。  
1.  入力 `100px` して、キーを押し `Enter` ます。  **ボックスモデル**の既定値はピクセルですが、やなどの他の値も受け取り `25%` `10vw` ます。  

> ##### 図 6  
> 要素のパディングの上にマウスポインターを置いたところ  
> ![要素のパディングの上にマウスポインターを置いたところ][ImageShowPadding]  

> ##### 図 7  
> 要素の左余白を変更する  
> ![要素の左余白を変更する][ImageChangeMargin]  

 



<!-- image links -->  

[ImageInspect]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me.msft.png "図 1: DOM ツリーで、検査された要素が強調表示されている"  
[ImageAloha]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me-styles.msft.png "図 2: 検査対象要素に適用されている CSS クラスが、[スタイル] タブで強調表示される"  
[ImageDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-background-color-to-me-styles-p.msft.png "図 3: [スタイル] タブを使用して要素に CSS 宣言を追加する"  
[ImageApplyClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-a-class-to-me-styles-cls.msft.png "図 4: 要素への color_me クラスの適用"  
[ImageSetHover]: /microsoft-edge/devtools-guide-chromium/media/css-elements-hover-over-me-styles-hov-hover.msft.png "図 5: 要素の hover 擬似開始の切り替え"  
[ImageShowPadding]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-padding.msft.png "図 6: 要素のパディングの上にマウスポインターを置いたところ"  
[ImageChangeMargin]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-margin-edit.msft.png "図 7: 要素の左余白を変更する"  

<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS の例-Microsoft Edge (Chromium) DevTools |故障"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/css/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
