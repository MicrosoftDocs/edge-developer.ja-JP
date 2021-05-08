---
description: 開発者ツールを使用して、縮小されたモーションをシミュレートします。
title: 開発者ツールを使用して縮小モーションをシミュレートする (CSS Prefers Reduced Motion)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 29cdbd7492665e819315910b3f743d444470cc12
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397868"
---
# <a name="reduced-motion-simulation"></a>モーション シミュレーションの削減  

Web 製品のアニメーションはアクセシビリティの問題である可能性があります。  オペレーティング システムは、ユーザーの混乱や、発作のトリガーなどの潜在的な正常性関連の問題を回避するためにアニメーションをオフにするオプションを含めて、この問題に対処します。  Web では、ユーザーがアニメーションを実行したり表示したりすることを好むのを検出するために、優先的に縮小 [されたモーション][MDNPrefersReducedMotion] CSS メディア クエリを使用できます。  製品では、影響を受けるユーザーにアニメーションが表示されるのを避けるために、テストでアニメーション コードをラップできます。  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

Microsoft [Edge DevTools を使用][DevtoolsIndex]すると、オペレーティング システムを変更することなく、この縮小モーション設定をシミュレートできます。  

1.  **コマンド メニュー** を開きます。  
    1.  `Control` + `Shift` + `P` Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **コマンド メニュー**  
        :::image-end:::  
        
1.  `reduced`「」と入力して、シミュレーションのオンとオフを切り替えます。  オプションを選択して選択します `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="[コマンド メニュー] から低いモーション設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       [コマンド メニュー] から低い **モーション設定をオン** または **オフにする**  
    :::image-end:::  
    
1.  現在のページを更新して、アニメーションがオフになっているか表示されているかどうかをテストします。  
    
<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "縮小モーション を優先|MDN"  
