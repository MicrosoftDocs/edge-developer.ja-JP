---
description: Microsoft Edge DevTools で視覚の不備をエミュレートします。
title: Microsoft Edge DevTools で視覚の不備をエミュレートする (色覚不覚)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5343d32992880f8c60501a86db6cb3a92f417331
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230825"
---
# 視覚欠陥をエミュレートする

色覚に不備があるユーザーのニーズ[][ColorblindawarenessMain]を満たすために[、Microsoft Edge DevTools][DevtoolsIndex]を使用すると、特定の色覚に対する不備をシミュレートできます。  **Emulate vision 不備ツールは**、次のカテゴリをシミュレートします。  

| 色覚に対する不備 | 詳細 |  
|:--- |:--- |  
| ぼやけた視覚 | ユーザーは詳細に焦点を当てに困難を持っています。 |   
| プロタニア語 | ユーザーは赤い光を認識できません。 |  
| Deuteranute | ユーザーは緑色の光を認識できません。 |  
| トリタニア | ユーザーは青色の光を認識できません。 |  
| Achromatopsia | ユーザーは色を認識できず、すべての色を灰色の網掛けに減らします。 |  

## レンダリング ツールに移動する  

Web 製品に適用されている視覚障害をシミュレートするには、レンダリング ツールを [開きます][DevtoolsRenderingToolsIndex]。  

1.  レンダリング ツールを開くには、ツール バーの `...` メニュー項目を選択します。  
1.  選択 `More tools`  
1.  選択 `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリング ツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       レンダリング ツール **を開く**  
    :::image-end:::  

レンダリング **メニュー** がドロワーに表示されます。  

1.  メニュー項目まで下にスクロールし、ドロップダウン メニューを `Emulate vision deficiencies` 選択してオプションを表示します。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダリング ドロワーの [Emulate Vision の不備] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       レンダリング**ドロワーの [Emulate vision の**不備]**メニュー**  
    :::image-end:::  
    
1.  オプションを選択します。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[Emulate Vision の不備] メニュー オプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       [ **エミュレートする視覚の不備] メニュー** オプション  
    :::image-end:::  
    
1.  メイン ウィンドウには、現在のページに適用されている選択したオプションのシミュレーションが表示されます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="[ぼやけた視覚** シミュレーションを使用して表示する]" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             ぼや **けた視覚シミュレーションを使用して表示** する  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Display using **Achromatopsia** simulation" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             **Achromatopsia シミュレーションを使用して表示**する :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## コマンド メニューを使用する  

コマンド メニューを使用 **して、さまざまな** シミュレーションにアクセスすることもできます。  

1.  `Control` + `Shift` + `P` \(Windows\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニュー**を開きます**。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  Type `emulate` , choose what you want to simulate and select `Enter` .  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンド メニューで使用できるさまざまなシミュレーション オプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       コマンド メニューで使用できるさまざまなシミュレーション **オプション**  
    :::image-end:::  
    
> [!IMPORTANT]
> **Emulate vision の不備ツールは**、各不備を持つ人が製品を見る方法の近似値をシミュレートします。  人は人それぞれ異なっているので、視覚に対する不備は人によって重大度が異なります。  ユーザーのニーズをより良く満たすために、問題になる可能性がある色の組み合わせは避ける必要があります。  **Emulate vision 不備ツール**は、製品の完全なアクセシビリティ評価ではありません。  代わりに **、Emulate vision 不備** ツールを使用すると、問題を回避するための良い第一歩を提供する必要があります。  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsRenderingToolsIndex]: ../rendering-tools/index.md "実行時のパフォーマンスを分析する |Microsoft Docs"  

[ColorblindawarenessMain]: http://www.colourblindawareness.org "視覚に対する意識向上組織"  

[AmfcbMain]: https://www.amfcb.org "カラー ブラインドのための American Foundation (AFCB)"  

