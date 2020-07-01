---
title: Microsoft Edge DevTools でビジョンの不備をエミュレートする (色覚障碍)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b70499fa189d162fa7589966bab183f4c12f68f7
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843922"
---
# ビジョンの欠陥のエミュレート

[カラービジョンの欠陥][ColorblindawarenessMain]を持つユーザーのニーズをより適切に満たすために、 [Microsoft Edge devtools][MicrosoftEdgeDevTools]を使用すると、特定の色ビジョンの不備をシミュレートすることができます。  **ビジョンのエミュレート**ツールでは、次のカテゴリがシミュレートされます。  

| カラービジョンの欠陥 | 詳細 |  
|:--- |:--- |  
| ぼやけたビジョン | ユーザーは、細かい詳細を重視しています。 |   
| Protanopia | ユーザーは赤のライトを認識できません。 |  
| Deuteranopia | ユーザーは、緑色の光を認識することはできません。 |  
| Tritanopia | ユーザーは青色の光を認識できません。 |  
| Achroopsia | ユーザーは色を認識することはできません。これにより、すべての色が灰色の階調に縮小されます。 |  

## レンダリングツールに移動する  

Web 製品に対してビジョンの欠陥が適用されていることをシミュレートするには、[レンダリングツール][RenderingTools]を開きます。  

1.  `...`ツールバーのメニュー項目を選択して、レンダリングツールを開く  
1.  選択する `More tools`  
1.  選択する `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリングツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       **レンダリングツール**を開く  
    :::image-end:::  

[**レンダリング**] メニューが [ドロアー] に表示されます。  

1.  メニュー項目まで下にスクロール `Emulate vision deficiencies` し、ドロップダウンメニューを選択してオプションを表示します。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダードロアーの [ビジョンの欠陥のエミュレート] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       **レンダー**ドロアーの [**ビジョンの欠陥のエミュレート**] メニュー  
    :::image-end:::  
    
1.  オプションを選択します。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[視覚障碍のエミュレート] メニューのオプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       [**視覚障碍のエミュレート**] メニューのオプション  
    :::image-end:::  
    
1.  メインウィンドウには、現在のページに適用されているオプションのシミュレーションが表示されます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="ディスプレイの使用 * * ぼやけたビジョン * * シミュレーション" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             ぼやけた**ビジョン**シミュレーションを使って表示する  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="* * Achromatopsia * * シミュレーションを使用して表示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             **Achromatopsia**シミュレーションを使った表示 :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## コマンドメニューを使用する  

**コマンドメニュー**を使用して、さまざまなシミュレーションにアクセスすることもできます。  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **コマンドメニュー**  
    :::image-end:::  
    
1.  「」と入力し `emulate` 、シミュレートするものを選択して、キーを押し `Enter` ます。  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンドメニューで使用できるさまざまなシミュレーションオプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       **コマンドメニュー**で使用できるさまざまなシミュレーションオプション  
    :::image-end:::  
    
> [!IMPORTANT]
> **ビジョンのエミュレート**ツールでは、各欠陥のあるユーザーが製品をどのように表示するかの概算をシミュレートします。  各ユーザーは異なるため、視覚障碍はユーザーによって深刻されます。  ユーザーのニーズをより適切に満たすために、問題が発生する可能性のある色の組み合わせは避けてください。  **ビジョンのエミュレート**ツールは、製品の完全なアクセシビリティ評価ではありません。  代わりに、**ビジョンの欠陥**ツールをエミュレートすることで、問題を回避するための最初の手順を行う必要があります。  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org "色覚障碍のある組織"  
[AmfcbMain]: https://www.amfcb.org "色ブラインド (AFCB) のアメリカの基盤"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge (Chromium) のレンダリングツール"  
