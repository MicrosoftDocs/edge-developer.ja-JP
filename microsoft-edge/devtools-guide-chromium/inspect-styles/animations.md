---
title: アニメーションを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6466c7f0e1f8680a2429b565e8022d152d05d733
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570344"
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





# アニメーションを検査する   



Microsoft Edge DevTools のアニメーションのインスペクターを使って、アニメーションの検査と変更を行います。  

> ##### 図 1  
> アニメーションの詳細設定  
> ![アニメーションの詳細設定][ImageAnimationInspector]  

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

*   [**カスタマイズ] および [コントロールの DevTools** ] メニューを開く  
    1.  [**その他のツール**] サブメニューに移動します。  
    1.  [**アニメーション**] を選択します。  
        
        > ##### 図 2  
        > メインメニューを使ったアニメーション  
        > ![メインメニューを使ったアニメーション][ImageAnimationsViaMainMenu]  
        
*   **コマンドメニュー**を開く  
    1.  「`Drawer: Show Animations`」と入力します。  

[アニメーションの設定] が、コンソールドロワーの横にタブとして開きます。  アニメーション検査は [引き出し] タブであるため、任意の DevTools パネルからアニメーションのインスペクターを使用できます。  

> ##### 図 3  
> 空のアニメーション検査  
> ![空のアニメーション検査][ImageEmptyAnimationInspector]  

アニメーションの検査は、4つのメインセクション \ (またはウィンドウ \) にグループ化されています。  このガイドでは、各ウィンドウについて次のことを示します。  

| | ウィンドウ | 説明 |  
| --- |:--- |:--- |  
| 件 | **コントロール** | ここでは、現在キャプチャされているすべてのアニメーショングループをクリアするか、現在選択されているアニメーショングループの速度を変更することができます。 |  
| 両面 | **概要** | ここでアニメーショングループを選択して、**詳細**ウィンドウで確認して変更します。 |  
| - | **タイムライン** | ここからアニメーションを一時停止して開始するか、アニメーション内の特定のポイントにジャンプします。 |  
| 4d | **詳細** | 現在選択されているアニメーショングループを検査して変更します。 |  

> ##### 図 4  
> 注釈付きアニメーションのインスペクター  
> ![注釈付きアニメーションのインスペクター][ImageAnnotatedAnimationInspector]  

アニメーションをキャプチャするには、アニメーションのインスペクターが開いている状態でアニメーションをトリガーする操作を実行します。  ページの読み込みでアニメーションがトリガーされた場合は、アニメーションインスペクターが開いた状態でページを再読み込みして、アニメーションを検出します。  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## アニメーションを検査する   

アニメーションをキャプチャした後は、いくつかの方法で再生できます。  

*   **概要**ウィンドウのサムネイルにマウスポインターを置くと、プレビューが表示されます。  
*   (**詳細**ウィンドウに表示されるように) [**概要**] ウィンドウで [アニメーション] グループを選び、 **[再生** ![ 再生] アイコンを押し ][ImageReplayButtonIcon] ます。  アニメーションはビューポートで再生されます。  アニメーション**速度**のアニメーション速度のアイコンをクリックして、 ![ ][ImageAnimationSpeedButtonsIcon] 現在選択されているアニメーショングループのプレビューの速度を変更します。  赤い垂直バーを使用して、現在の位置を変更することができます。  
*   赤い垂直バーをクリックしてドラッグすると、ビューポートのアニメーションがスクラブされます。  

### アニメーションの詳細の表示  

アニメーショングループをキャプチャしたら、[**概要**] ウィンドウでクリックして詳細を表示します。  **詳細**ウィンドウには、個々のアニメーションに1行が割り当てられます。  

> ##### 図 5  
> アニメーショングループの詳細  
> ![アニメーショングループの詳細][ImageAnimationGroupDetails]  

アニメーションの上にマウスポインターを移動すると、ビューポート内で強調表示されます。  アニメーションをクリックして、[**要素**] パネルで選択します。  

> ##### 図 6  
> ビューポートでアニメーションをポイントして強調表示する  
> ![ビューポートでアニメーションをポイントして強調表示する][ImageHoverOverAnimationHighlightViewport]  

アニメーションの左端、濃い色の部分が定義です。  右側の [薄い色] セクションは、反復計算を表します。  たとえば、[図 7](#figure-7)では、セクション2と3はセクション1のイテレーションを表します。  

> ##### 図 7  
> アニメーションの反復計算の図  
> ![アニメーションの反復計算の図][ImageDiagramAnimationIterations]  

2つの要素に同じアニメーションが適用されている場合、アニメーションのインスペクターでは要素に同じ色が割り当てられます。  色はランダムであり、意味はありません。  たとえば、[図 8](#figure-8)の2つの要素 `div.cwccw.earlier` と、要素との間に `div.cwccw.later` 同じアニメーション \ ( `spinrightleft` \) が適用されてい `div.ccwcw.earlier` `div.ccwcw.later` ます。  

> ##### 図 8  
> 色分けされたアニメーション  
> ![色分けされたアニメーション][ImageColorCodedAnimations]  

## アニメーションの変更   

アニメーションインスペクターでアニメーションを変更するには、次の3つの方法があります。  

*   アニメーションの継続時間。  
*   キーフレームのタイミング。  
*   開始タイミングの遅延。  

このセクションでは、[図 9](#figure-9)は元のアニメーションを表していることを想定しています。  

> ##### 図 9  
> 変更前の元のアニメーション  
> ![変更前の元のアニメーション][ImageOriginalAnimationBeforeModification]  

アニメーションの継続時間を変更するには、最初または最後の円をクリックしてドラッグします。  

> ##### 図 10  
> 変更された期間  
> ![変更された期間][ImageModifiedDuration]  

アニメーションでキーフレームルールが定義されている場合は、それらは白色の内側の円として表されます。  いずれかをクリックしてドラッグし、キーフレームのタイミングを変更します。  

> ##### 図 11  
> 変更されたキーフレーム  
> ![変更されたキーフレーム][ImageModifiedKeyframe]  

アニメーションに遅延を追加するには、円以外の任意の場所でクリックしてドラッグします。  

> ##### 図 12  
> 変更遅延  
> ![変更遅延][ImageModifiedDelay]  

<!--   -->  



<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: /microsoft-edge/devtools-guide-chromium/media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/replay-button-icon.msft.png  

[ImageAnimationInspector]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations-completed.msft.png "図 1: アニメーションインスペクター"  
[ImageAnimationsViaMainMenu]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-more-tools-animations.msft.png "図 2: メインメニューを使ったアニメーション"  
[ImageEmptyAnimationInspector]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations.msft.png "図 3: 空のアニメーションインスペクター"  
[ImageAnnotatedAnimationInspector]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png "図 4: 注釈付きアニメーションのインスペクター"  
[ImageAnimationGroupDetails]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png "図 5: アニメーショングループの詳細"  
[ImageHoverOverAnimationHighlightViewport]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png "図 6: ビューポートでアニメーションをポイントして強調表示する"  
[ImageDiagramAnimationIterations]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-display-animations-highlight.msft.png "図 7: アニメーションの反復の図"  
[ImageColorCodedAnimations]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-display-animations.msft.png "図 8: 色分けされたアニメーション"  
[ImageOriginalAnimationBeforeModification]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations.msft.png "図 9: 変更前の元のアニメーション"  
[ImageModifiedDuration]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png "図 10: 変更された期間"  
[ImageModifiedKeyframe]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png "図 11: 変更されたキーフレーム"  
[ImageModifiedDelay]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png "図 12: 変更の遅延"  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
