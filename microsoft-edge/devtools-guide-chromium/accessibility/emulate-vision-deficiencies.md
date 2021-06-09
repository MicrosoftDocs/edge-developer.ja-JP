---
description: DevTools のビジョンのMicrosoft Edgeエミュレートします。
title: DevTools の視覚Microsoft Edgeをエミュレートする (色覚不備)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0a0ee09c2f739beb366b4c39d113b31fb719ec6a
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597122"
---
# <a name="emulate-vision-deficiencies"></a>視覚欠陥をエミュレートする  

色覚障害[\(color][ColorblindawarenessMain] blindness\) またはぼやけた視力を持つユーザーのニーズをよりよく満たすために[、Microsoft Edge DevTools][DevtoolsIndex]を使用すると、ぼやけた視力と特定の色覚の欠陥をシミュレートできます。  [ **ビジョンの不備のエミュレート]** ツールは、次のカテゴリをシミュレートします。  

| 色覚の不足 | 詳細 |  
|:--- |:--- |  
| ぼやけたビジョン | ユーザーは詳細に焦点を当てるのが困難です。 |  
| Protanopia | ユーザーは赤い光を認識できません。 |  
| Deuteranopia | ユーザーは緑色の光を認識できません。 |  
| トリタニア | ユーザーは青色光を認識できません。 |  
| アクロマトプシア | ユーザーは色を認識できず、すべての色が灰色の色合いに減少します。 |  


## <a name="navigate-to-the-rendering-tool"></a>[レンダリング] ツールに移動する

Web 製品に適用されているビジョン不足をシミュレートするには、[レンダリング ツール] を [開きます][DevtoolsRenderingToolsIndex]。  

1.  レンダリング ツールを開く場合は、ツールバー `...` のメニュー項目を選択します。  
1.  その他 **のツールを選択する**  
1.  [レンダリング **] を選択する**  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリング ツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       レンダリング ツール **を開** く
    :::image-end:::  
    
[ **レンダリング]** メニューがドロワーに表示されます。  

1.  メニュー項目まで下 `Emulate vision deficiencies` にスクロールし、ドロップダウン メニューを選択してオプションを表示します。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダリング ツールの [ビジョンの不備のエミュレート] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       レンダリング**ツールの [ビジョンの不備****のエミュレート**] メニュー
    :::image-end:::  
    
1.  オプションを選択します。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[ビジョンの不備のエミュレート] メニュー オプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       [ **エミュレートビジョンの欠陥] メニュー** オプション  
    :::image-end:::  
    
1.  メイン ウィンドウには、現在のページに適用された選択したオプションのシミュレーションが表示されます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="ぼやけたビジョン シミュレーションを使用して表示する" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             ぼや **けたビジョン シミュレーションを使用して表示** する  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Achromatopsia シミュレーションを使用した表示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             **Achromatopsia シミュレーションを使用した**表示 :::image-end:::  
       :::column-end:::
    :::row-end:::
    

## <a name="use-the-command-menu"></a>コマンド メニューを使用する  

コマンド メニューを使用 **して、** さまざまなシミュレーションにアクセスすることもできます。  

1.  `Ctrl` + `Shift` + `P` コマンド メニューを開Windows `Command` + `Shift` + `P` \(Windows/Linux\) または \(macOS\)**を選択します**。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  [種類 `emulate` ] をクリックし、シミュレートする条件を選択して選択します `Enter` 。  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンド メニューで使用できるさまざまなシミュレーション オプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       コマンド メニューで使用できるさまざまなシミュレーション **オプション**  
    :::image-end:::  
    
> [!IMPORTANT]
> エミュレート **ビジョンの欠陥ツールは** 、各欠陥を持つ人物が製品を見る方法の近似をシミュレートします。  一人一人が異なるので、視力の欠陥は人によって重症度が異なります。  ユーザーのニーズをよりよく満たすために、問題になる可能性がある色の組み合わせを避ける必要があります。  エミュレート **ビジョンの欠陥ツール** は、製品の完全なアクセシビリティ評価ではありません。  代わりに、 **エミュレートビジョンの欠陥** ツールは、問題を回避するための良い最初のステップを提供する必要があります。  


## <a name="see-also"></a>関連項目

* [ページがぼやけたビジョンで使用できると確認する](test-blurred-vision.md)


<!-- links -->  
[DevToolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsRenderingToolsIndex]: ../rendering-tools/index.md "ランタイム パフォーマンス の分析|Microsoft Docs"  

[ColorblindawarenessMain]: https://www.colourblindawareness.org "カラー ブラインドの認識組織"  

[AmfcbMain]: https://www.amfcb.org "カラー ブラインド (AFCB) のアメリカンファンデーション"  
