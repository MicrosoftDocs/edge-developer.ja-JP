---
description: Microsoft Edge DevTools のアニメーションのインスペクターを使って、アニメーションの検査と変更を行います。
title: アニメーションの検査
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fed686c07acd0648ac512dac131d85a317fb64eb
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124776"
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

# アニメーションの検査  

Microsoft Edge DevTools のアニメーションのインスペクターを使って、アニメーションの検査と変更を行います。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   アニメーションの詳細設定  
:::image-end:::  

### まとめ  

*   アニメーションインスペクターを開いてアニメーションをキャプチャします。  アニメーションの検査機能により、アニメーションが自動的に検出され、グループに並べ替えられます。  
*   1つずつ減速して、1つずつ再生するか、ソースコードを表示して、アニメーションを検査します。  
*   タイミング、遅延、再生時間、またはキーフレームのオフセットを変更して、アニメーションを変更します。  

## 概要  

Microsoft Edge DevTools アニメーションのインスペクターには、2つの主な目的があります。  

*   アニメーションの検査。  アニメーショングループのソースコードを減速、再生、検査します。  
*   アニメーションの変更。  アニメーショングループのタイミング、遅延、再生時間、またはキーフレームのオフセットを変更します。  ベジエ編集とキーフレーム編集は現在サポートされていません。  

アニメーションのインスペクターでは、CSS アニメーション、CSS 切り替え、web アニメーションがサポートされています。  `requestAnimationFrame` アニメーションは現在サポートされていません。  

### アニメーショングループとは  

アニメーショングループは、互いに関連している可能性のあるアニメーションのグループです。  現時点では、web にはグループアニメーションの実際の概念はありません。このため、アニメーションが1つの一貫した視覚効果としてレンダリングされるように、モーションデザイナーと開発者は個々のアニメーションを作成して時間を設定する必要があります。  アニメーションの設定では、開始時刻 \ (遅延を除く) に基づいて、どのアニメーションが関連しているかが予測されます。  アニメーションのインスペクターでは、アニメーションを並べてグループ化することもできます。  
つまり、同じスクリプトブロックですべてトリガーされる一連のアニメーションは一緒にグループ化されます。  アニメーションが非同期の場合は、別のグループに配置されます。  

## 使ってみる  

アニメーションインスペクターを開くには、次の2つの方法があります。  

*   [ **カスタマイズ] および [コントロールの DevTools** ] メニューを開く  
    1.  [ **その他のツール** ] サブメニューに移動します。  
    1.  [ **アニメーション**] を選択します。  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           メインメニューを使用する**アニメーション**  
    :::image-end:::  
        
*   **コマンドメニュー**を開く  
    1.  「`Drawer: Show Animations`」と入力します。  

[アニメーションの設定] が、コンソールドロワーの横にタブとして開きます。  アニメーション検査は [引き出し] タブであるため、任意の DevTools パネルからアニメーションのインスペクターを使用できます。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   空のアニメーション検査  
:::image-end:::  

アニメーションの検査は、4つのメインセクション \ (またはウィンドウ \) にグループ化されています。  このガイドでは、各ウィンドウについて次のことを示します。  

| インデックス | ウィンドウ | 説明 |  
|:--- |:--- |:--- |  
| 件 | **コントロール** | ここでは、現在キャプチャされているすべてのアニメーショングループをクリアするか、現在選択されているアニメーショングループの速度を変更することができます。 |  
| 両面 | **概要** | ここでアニメーショングループを選択して、 **詳細** ウィンドウで確認して変更します。 |  
| - | **タイムライン** | ここからアニメーションを一時停止して開始するか、アニメーション内の特定のポイントにジャンプします。 |  
| 4d | **詳細** | 現在選択されているアニメーショングループを検査して変更します。 |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   注釈付きアニメーションのインスペクター  
:::image-end:::  

アニメーションをキャプチャするには、アニメーションのインスペクターが開いている状態でアニメーションをトリガーする操作を実行します。  ページの読み込みでアニメーションがトリガーされた場合は、アニメーションインスペクターが開いた状態でページを再読み込みして、アニメーションを検出します。  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## アニメーションの検査  

アニメーションをキャプチャした後は、いくつかの方法で再生できます。  

*   **概要**ウィンドウのサムネイルにマウスポインターを置くと、プレビューが表示されます。  
*   **概要**ウィンドウ (**詳細**ウィンドウに表示されるように) から [アニメーション] グループを選び、 **[再生**] ([ ![ 再生] アイコン ][ImageReplayButtonIcon] \) アイコンを押します。  アニメーションはビューポートで再生されます。  **animation speed** ![ ][ImageAnimationSpeedButtonsIcon] 現在選択されているアニメーショングループのプレビューの速度を変更するには、[アニメーションの速度] (アニメーションの速度のアイコン) アイコンをクリックします。  赤い垂直バーを使用して、現在の位置を変更することができます。  
*   赤い垂直バーをクリックしてドラッグすると、ビューポートのアニメーションがスクラブされます。  
    
### アニメーションの詳細の表示  

アニメーショングループをキャプチャしたら、[ **概要** ] ウィンドウでクリックして詳細を表示します。  **詳細**ウィンドウには、個々のアニメーションに1行が割り当てられます。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   アニメーショングループの詳細  
:::image-end:::  

アニメーションの上にマウスポインターを移動すると、ビューポート内で強調表示されます。  アニメーションをクリックして、[ **要素** ] パネルで選択します。  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   ビューポートでアニメーションをポイントして強調表示する  
:::image-end:::  

アニメーションの左端、濃い色の部分が定義です。  右側の [薄い色] セクションは、反復計算を表します。  たとえば、次の図では、セクション2と3はセクション1のイテレーションを表しています。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   アニメーションの反復計算の図  
:::image-end:::  

2つの要素に同じアニメーションが適用されている場合、アニメーションのインスペクターでは要素に同じ色が割り当てられます。  色はランダムであり、意味はありません。  たとえば、次の図では、要素と要素と同様に、2つの要素 `div.cwccw.earlier` と、 `div.cwccw.later` 同じアニメーション \ ( `spinrightleft` \) が適用されてい `div.ccwcw.earlier` `div.ccwcw.later` ます。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   色分けされたアニメーション  
:::image-end:::  

## アニメーションの変更  

アニメーションインスペクターでアニメーションを変更するには、3つの方法があります。  

*   アニメーションの継続時間。  
*   キーフレームのタイミング。  
*   開始タイミングの遅延。  
    
次の図では、元のアニメーションが表示されています。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   変更前の元のアニメーション  
:::image-end:::  

アニメーションの継続時間を変更するには、最初または最後の円をクリックしてドラッグします。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   変更された期間  
:::image-end:::  

アニメーションでキーフレームルールが定義されている場合は、それらは白色の内側の円として表されます。  いずれかをクリックしてドラッグし、キーフレームのタイミングを変更します。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   変更されたキーフレーム  
:::image-end:::  

アニメーションに遅延を追加するには、円以外の任意の場所でクリックしてドラッグします。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   変更遅延  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: ../media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: ../media/replay-button-icon.msft.png  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
