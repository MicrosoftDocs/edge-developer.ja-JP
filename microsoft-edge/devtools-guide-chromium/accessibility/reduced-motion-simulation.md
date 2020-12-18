---
description: 開発者ツールを使用して、縮小されたモーションをシミュレートします。
title: 開発者ツールを使用して縮小モーションをシミュレートする (CSS Prefers Reduced Motion)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0e5243e01ca6c9344dceffb0bf004dadccc3d4d7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230790"
---
# モーション シミュレーションの削減  

Web 製品のアニメーションはアクセシビリティの問題である可能性があります。  オペレーティング システムは、ユーザーの混乱や、発作のトリガーなどの潜在的な健康関連の問題を回避するためにアニメーションをオフにするオプションを含めて、この問題に対処します。  Web では、ユーザーがアニメーションを表示しない場合に [、prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query を使用して検出できます。  製品では、影響を受けるユーザーにアニメーションが表示されるのを避けるために、テストでアニメーション コードをラップすることができます。  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

Microsoft [Edge DevTools を][DevtoolsIndex]使用すると、オペレーティング システムを変更することなく、この縮小されたモーション設定をシミュレートできます。  

1.  コマンド メニュー **を開きます**。  
    1.  `Control` + `Shift` + `P` Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **コマンド メニュー**  
        :::image-end:::  
        
1.  シミュレーション `reduced` をオンまたはオフにする場合は、「入力」と入力します。  オプションを選択し、選択します `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="コマンド メニューの [優先されるモーションの縮小] 設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       コマンド メニューの [優先されるモーション **の縮小] 設定を** オンまたは **オフにする**  
    :::image-end:::  
    
1.  現在のページを更新して、アニメーションがオフになっているか表示されているかどうかをテストします。  
    
<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion |MDN"  
