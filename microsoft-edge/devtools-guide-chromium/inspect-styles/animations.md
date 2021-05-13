---
description: DevTools アニメーション インスペクターでアニメーションMicrosoft Edge変更します。
title: アニメーションの検査
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a695517cb56da057e62293b5ca92b22058602f44
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564218"
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
# <a name="inspect-animations"></a>アニメーションの検査  

DevTools アニメーション インスペクターでアニメーションMicrosoft Edge変更します。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="アニメーション インスペクター" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   アニメーション インスペクター  
:::image-end:::  

### <a name="summary"></a>要約  

*   アニメーション インスペクターを開いてアニメーションをキャプチャします。  アニメーション インスペクターは、アニメーションを自動的に検出し、グループに並べ替える。  
*   アニメーションを検査するには、各アニメーションの速度を低下したり、各アニメーションを再生したり、ソース コードを表示したりします。  
*   タイミング、遅延、期間、またはキーフレーム のオフセットを変更してアニメーションを変更します。  

## <a name="overview"></a>概要  

DevTools Microsoft Edgeインスペクターには、主に 2 つの目的があります。  

*   アニメーションの検査。  アニメーション グループのソース コードの速度を低下、再生、または検査する場合。  
*   アニメーションの変更。  アニメーション グループのタイミング、遅延、期間、またはキーフレーム のオフセットを変更する場合。  ベジエ編集とキーフレーム編集は現在サポートされていません。  

アニメーション インスペクターは、CSS アニメーション、CSS 切り替え、および Web アニメーションをサポートします。  `requestAnimationFrame` アニメーションは現在サポートされていません。  

### <a name="what-is-an-animation-group"></a>アニメーション グループとは  

アニメーション グループは、互いに関連付け合う可能性があるアニメーションのグループです。  現時点では、Web にはグループ アニメーションの実際の概念はないので、モーション デザイナーと開発者は、アニメーションが 1 つの一貫性のある視覚効果としてレンダリングするために、個々のアニメーションを作成して時間を取る必要があります。  アニメーション インスペクターは、開始時刻 \(遅延を除く、および on\) に基づいて関連するアニメーションを予測します。  アニメーション インスペクターは、アニメーションを並べてグループ化します。  
つまり、同じスクリプト ブロックでトリガーされるアニメーションのセットがグループ化されます。  アニメーションが非同期の場合は、別のグループに配置されます。  

## <a name="get-started"></a>作業の開始  

アニメーション インスペクターを開く方法は 2 通りあります。  

*   **[DevTools のカスタマイズと制御] メニューを開**きます。  
    1.  [その他の **ツール] サブメニュー** に移動します。  
    1.  [アニメーション **] を選択します**。  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="メイン メニューを使用したアニメーション" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           **メイン メニュー** を使用したアニメーション  
        :::image-end:::  
        
*   コマンド メニュー **を開く**  
    1.  「`Drawer: Show Animations`」と入力します。  
        
[アニメーション インスペクタ] が [コンソール] ツールの横 **に開** きます。  アニメーション インスペクターはドロワー ツールですから、任意の DevTools パネルからアニメーション インスペクターを使用できます。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="空のアニメーションインスペクター" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   空のアニメーションインスペクター  
:::image-end:::  

アニメーション インスペクターは、4 つのメイン セクション \(または panes\) にグループ化されます。  このガイドでは、各ウィンドウを次のように参照します。  

| インデックス | ウィンドウ | 説明 |  
|:--- |:--- |:--- |  
| 1 | **コントロール** | ここから、現在キャプチャされているすべてのアニメーション グループをクリアするか、現在選択されているアニメーション グループの速度を変更できます。 |  
| 2 | **概要** | [詳細] ウィンドウでアニメーション グループを検査および変更するには、ここで [アニメーション グループ] **を選択** します。 |  
| 3 | **タイムライン** | ここからアニメーションを一時停止して開始するか、アニメーション内の特定のポイントにジャンプします。 |  
| 4 | **詳細** | 現在選択されているアニメーション グループを検査および変更します。 |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="注釈付きアニメーションインスペクター" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   注釈付きアニメーションインスペクター  
:::image-end:::  

アニメーションをキャプチャするには、アニメーション インスペクターが開いている間にアニメーションをトリガーする操作を実行します。  ページの読み込み時にアニメーションがトリガーされた場合は、[アニメーション インスペクター] を開いた状態でページを更新して、アニメーションを検出します。  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <a name="inspect-animations"></a>アニメーションの検査  

アニメーションをキャプチャした後、再生する方法は次のとおりです。  

*   [概要] ウィンドウのサムネイルに **カーソルを合わせる** と、プレビューが表示されます。  
*   [概要] ウィンドウ**\([** 詳細] ウィンドウ\に表示される****) から [アニメーション グループ] を選択し、再生**\(** 再生アイコン ![ \) アイコン ](../media/replay-button-icon.msft.png) を選択します。  アニメーションはビューポートで再生されます。  現在選択 **されているアニメーション** グループのプレビュー速度を変更するには、アニメーション速度 \( アニメーション速度アイコン ![ ](../media/animation-speed-buttons-icon.msft.png) \) アイコンを選択します。  赤い垂直バーを使用して現在の位置を変更できます。  
*   赤い垂直バーを選択してドラッグして、ビューポート アニメーションをスクラブします。  
    
### <a name="view-animation-details"></a>アニメーションの詳細を表示する  

アニメーション グループをキャプチャした後、[概要] ウィンドウからアニメーション グループを **選択** して詳細を表示します。  [詳細 **] ウィンドウ** では、各アニメーションに行が割り当てられます。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="アニメーション グループの詳細" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   アニメーション グループの詳細  
:::image-end:::  

アニメーションにカーソルを合わせると、ビューポート内でアニメーションが強調表示されます。  [要素] ツールでアニメーションを選択して **選択** します。  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="アニメーションにカーソルを合わせると、ビューポートでアニメーションが強調表示されます。" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   アニメーションにカーソルを合わせると、ビューポートでアニメーションが強調表示されます。  
:::image-end:::  

アニメーションの左端の暗いセクションは定義です。  右側の色あせたセクションは、反復を表します。  たとえば、次の図では、セクション 2 とセクション 3 はセクション 1 の反復を表します。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="アニメーションの反復の図" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   アニメーションの反復の図  
:::image-end:::  

2 つの要素に同じアニメーションが適用されている場合、アニメーション インスペクターは同じ色を要素に割り当てる。  色はランダムで、意味はありません。  たとえば、次の図では、2 つの要素と同じ `div.cwccw.earlier` アニメーション \( \) が適用されます。要素と同様 `div.cwccw.later` `spinrightleft` `div.ccwcw.earlier` `div.ccwcw.later` です。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="色分けされたアニメーション" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   色分けされたアニメーション  
:::image-end:::  

## <a name="modify-animations"></a>アニメーションの変更  

アニメーション インスペクターを使用してアニメーションを変更するには、3 つの方法があります。  

*   アニメーションの期間。  
*   キーフレームのタイミング。  
*   開始時間の遅延。  
    
次の図では、元のアニメーションが表されています。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="変更前の元のアニメーション" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   変更前の元のアニメーション  
:::image-end:::  

アニメーションの期間を変更するには、最初または最後の円を選択してドラッグします。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="変更された期間" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   変更された期間  
:::image-end:::  

アニメーションでキーフレーム ルールが定義されている場合、これらは白い内側の円として表されます。  これらの 1 つを選択してドラッグして、キーフレームのタイミングを変更します。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="変更されたキーフレーム" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   変更されたキーフレーム  
:::image-end:::  

アニメーションに遅延を追加するには、円以外の任意の場所を選択してドラッグします。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="変更された遅延" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   変更された遅延  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
