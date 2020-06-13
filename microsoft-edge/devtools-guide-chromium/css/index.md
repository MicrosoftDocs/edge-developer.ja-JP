---
title: CSS の表示と変更の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 346145a7deb9e8ac951ed0578a5060da72817463
ms.sourcegitcommit: a34858dd3260967ba9699842fa839c7a94775fe4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2020
ms.locfileid: "10710386"
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

# CSS の表示と変更の概要  

Microsoft Edge DevTools を使用して、ページの CSS を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。  

## CSS の例を開く  

1.  `Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **CSS の例**] を選択して新しいウィンドウで開きます。  
    
    [CSS の例][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > [Devtools ウィンドウ][DevToolsCustomizePlacement]をビューポート \ (次の図のように表示) の右側にドッキングする場合は、[ **Devtools のカスタマイズと制御**] を選び `...` ます。  [ **DevTools のカスタマイズと制御**] ドロップダウンメニューの [ **dock** ] セクションで、[ **dock to right**] を選びます。  
    
## 要素の CSS を表示する  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストをポイントし `Inspect Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。  
    1.  DevTools の [**要素**] パネルで、[ **DOM Tree** ] タブの `Inspect Me!` 要素が強調表示されています。  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="DOM ツリーで、検査された要素が強調表示される" lightbox="../media/css-elements-inspect-me.msft.png":::
           図 1: **DOM ツリー**で、検査された要素が強調表示されている  
        :::image-end:::  
        
    1.  要素で、 `Inspect Me!` 属性の値を見つけ `data-message` てコピーします。  
1.  ページの [**値] `data-message` :** textbox で、値を入力します。  
1.  テキストをポイントし `Inspect Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。  
    1.  [DevTools] の [**要素**] パネルで、[**スタイル**] タブを選択します。  
    1.  [**スタイル**] タブに、 `Inspect Me!` 要素が強調表示されています。  
    1.  要素で、 `Inspect Me!` クラスの規則を見つけ `aloha` ます。  
        
        > [!NOTE]
        > この規則は、要素に適用されているために表示され `Inspect Me!` ます。  
        
    1.  クラスで、 `aloha` スタイルの値を見つけ `padding` てコピーします。  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="[スタイル] タブの [検査] 要素に適用されている CSS クラスが強調表示されている" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           図 2: 選択した要素に適用される CSS クラス ( `aloha` [**スタイル**] タブに表示される)  
        :::image-end:::  
        
1.  ページの [**値] `padding` :** textbox で、値を入力します。  

## 要素に CSS 宣言を追加する  

要素に CSS 宣言を変更したり追加したりするときは、[**スタイル**] タブを使います。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストをポイントし `Add A Background Color To Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。  
1.  [ `element.style` **スタイル**] タブの上部付近を選択します。  
1.  入力 `background-color` して、キーを押し `Enter` ます。  
1.  入力 `honeydew` して、キーを押し `Enter` ます。  **DOM ツリー**で、インラインスタイル宣言が要素に適用されていることを確認します。  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="[スタイル] タブを使用した要素への CSS 宣言の追加" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       図 3: `background-color:honeydew` 宣言は `element.style` 、[**スタイル**] タブのセクションを使って要素に適用されています。  
    :::image-end:::  
    
## CSS クラスを要素に追加する  

[**スタイル**] タブを使って、要素に対して CSS クラスを適用または削除したときの要素の外観を確認します。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストをポイントし `Add A Class To Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。  
1.  **Cls**を選びます。  DevTools は、選択した要素にクラスを追加できるテキストボックスを表示します。  
1.  `color_me`[**新しいクラスの追加**] テキストボックスに入力して、キーを押し `Enter` ます。  [**新しいクラスの追加**] テキストボックスの下に、クラスのオンとオフを切り替えることができるチェックボックスが表示されます。  `Add A Class To Me!`要素に他のクラスが適用されている場合は、それぞれのクラスをここから切り替えることもできます。  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="要素への color_me クラスの適用" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       図 4: `color_me` [**スタイル**] タブの [ **cls** ] セクションを使用して、クラスが要素に適用されている  
    :::image-end:::  
    
## 疑似状態をクラスに追加する  

[**スタイル**] タブを使って、CSS の疑似条件を要素に永続的に適用します。  Devtools では、、、、という機能がサポートさ `:active` `:focus` `:hover` れてい `:visited` ます。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストの上にマウスポインターを置き `Hover Over Me!` ます。  背景色が変更されます。  
1.  テキストをポイントし `Hover Over Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。  
1.  [**スタイル**] タブで、 **: hov**を選びます。  
1.  [ **: Hover** ] チェックボックスをオンにします。  実際には、要素の上にマウスポインターを置いていない場合でも背景色は変わります。  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="要素の hover 擬似状態の切り替え" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       図 5: `:hover` 要素の擬似状態の切り替え  
    :::image-end:::  
    
## 要素のサイズを変更する  

[**スタイル**] タブの**Box モデル**対話型ダイアグラムを使用して、要素の幅、高さ、パディング、余白、または境界線の長さを変更します。  

> [!NOTE]
> この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。  

1.  [CSS の例を開き](#open-css-examples)ます。  
1.  テキストをポイントし `Change My Margin!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。  
1.  **ボックスモデル**図の [**スタイル**] タブで、**パディング**の上にマウスポインターを置きます。  ビューポートで要素のパディングが強調表示されています。  

    > [!NOTE]
    > DevTools ウィンドウのサイズによっては、[**スタイル**] タブの下部にスクロールして、**ボックスモデル**を表示しなければならない場合があります。  

1.  **ボックスモデル**の左余白をダブルクリックします。現在のところ、 `-` 要素には左余白がない意味の値が含まれています。  
1.  入力 `100px` して、キーを押し `Enter` ます。  **ボックスモデル**の既定値はピクセルですが、やなどの他の値も受け取り `25%` `10vw` ます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="要素のパディングの上にマウスポインターを置いたところ" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             図 6: 要素のパディングの上にマウスポインターを置いたところ  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="要素の左余白を変更する" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             図 7: 要素の左余白を変更する  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## メディアクエリのデバッグ  

[メディアクエリ][MDNUsingMediaGueries]は、web 製品が各ユーザーの構成設定の変更に反応するようにするための手段です。  最も重要なユースケースは、ビューポートのサイズに応じて、さまざまな CSS レイアウトで製品を提供することです。  別のレイアウトを使用すると、モバイルデバイスと複数列のレイアウトのための1段のレイアウトが可能になります。利用可能な画面領域が増えます。  

CSS で定義したメディアクエリをデバッグまたはテストする場合は、次の手順を実行します。  

1.  開発者ツールを開き、左上の [**デバイスの切り替え] ツールバー**アイコンをクリックするか、 `Ctrl` + `Shift` + `M` \ ( `Cmd` + `Shift` + `M` macOS の場合) を押します。  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="デバイスのツールバーを開く" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       図 8: デバイスのツールバーを開く  
    :::image-end:::  
    
1.  デバイスツールバーを開き、右上のメニューを選択して、 `...` [**メディアクエリの表示**] を選択します。  ページの表示の上に、さまざまなメディアクエリを示す色付きのバーが表示されます。  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="デバイスツールバーでメディアクエリを表示する" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       図 9: デバイスのツールバーでメディアクエリを表示する  
    :::image-end:::  
    
1.  バーの境界線にマウスポインターを置くと、さまざまなメディアクエリの値が表示されます。 一致させる web ページのサイズを変更するには、それぞれを選びます。  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="プレビューバーからメディアクエリを選ぶ" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       図 10: プレビューバーからメディアクエリを選ぶ  
    :::image-end:::  
    
1.  メディアクエリをデバッグして、エディターで CSS ファイルを開くには、 `Sources` いずれかのバーセグメントにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開いて、を選択し `reveal in source code` ます。  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="ソースエディターでメディアクエリを見つける" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       図 11: ソースエディターでメディアクエリを見つける  
    :::image-end:::  
    
<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS の例-Microsoft Edge (Chromium) DevTools |故障"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディアクエリを使用する |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/css/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
