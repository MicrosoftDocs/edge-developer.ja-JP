---
title: Microsoft Edge DevTools でビジョンの不備をエミュレートする (色覚障碍)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0b608f5fe67724eee81aeb993577ee9b45cbca09
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758122"
---
# ビジョンの欠陥のエミュレート

世界中の約8% の男性と0.5% は、"色覚障碍" と呼ばれる、一般的に[色ビジョンの欠陥][ColorblindawarenessMain]になっています。  [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使うと、さまざまな既知の欠陥をエミュレートし、製品のプレビューを表示して確認することができます。  

| 色の欠陥 | 詳細 |  
|:--- |:--- |  
| ぼやけたビジョン |  |   
| Protanopia | 赤の光を感じることはできません。 |  
| Deuteranopia | 緑の光を感じることはできません。 |  
| Tritanopia | 青い光を感じることはできません。 |  
| Achroopsia | 灰色の階調を除き、どの色もまったく感じられません。 |  

## レンダリングツールに移動する  

現在の web 製品で色の欠陥をテストするには、[レンダリングツール][RenderingTools]を開きます。  

1.  `...`ツールバーのメニュー項目を選択して、レンダリングツールを開く  
1.  選択する `More tools`  
1.  選択する `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリングツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       **レンダリングツール**を開く  
    :::image-end:::  

**レンダリング**メニューは、devtools の下半分に表示されます。  

1.  メニュー項目まで下にスクロール `Emulate Vision deficiencies` して、オプションから選びます。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダリングツールの [ビジョンの欠陥のエミュレート] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       **レンダリング**ツールの [**ビジョンの欠陥のエミュレート**] メニュー  
    :::image-end:::  
    
1.  いずれかのオプションを選びます。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[視覚障碍のエミュレート] メニューのオプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       [**視覚障碍のエミュレート**] メニューのオプション  
    :::image-end:::  
    
1.  現在のページは、選択した欠陥によってユーザーにどのように表示されるかをシミュレートして表示されます。  

    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="Microsoft Edge 開発者ツールのドキュメント (ぼやけたビジョンエミュレーション)" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             ぼやけた**ビジョン**エミュレーションを使用して表示される  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Achroopsia のビジョンエミュレーションの Microsoft Edge 開発者ツールのドキュメント" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             **Achromatopsia のビジョン**エミュレーションを使用して表示する :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## コマンドメニューを使用する  

また、**コマンドメニュー**を使用してさまざまなメニューを表示することなく、さまざまなエミュレーションにアクセスできます。  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **コマンドメニュー**  
    :::image-end:::  
    
1.  「」と入力し `emulate` 、シミュレートするものを選択して、キーを押し `Enter` ます。  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンドメニューで使用できるさまざまなエミュレーションオプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       **コマンドメニュー**で使用できるさまざまなエミュレーションオプション  
    :::image-end:::  
    
> [!IMPORTANT]
> エミュレーションツールは、各不具合のあるユーザーが製品をどのように表示するかを概算したものです。  各ユーザーは異なるため、視覚障碍はユーザーによって深刻されます。  ユーザーのニーズをより適切に満たすために、問題が発生する可能性のある色の組み合わせは避けてください。  エミュレーションツールは製品のアクセシビリティを完全に評価するわけではありませんが、最大の欠点を回避するための第一歩として最適です。  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org "色覚障碍のある組織"  
[AmfcbMain]: https://www.amfcb.org "色ブラインド (AFCB) のアメリカの基盤"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge (Chromium) のレンダリングツール"  
