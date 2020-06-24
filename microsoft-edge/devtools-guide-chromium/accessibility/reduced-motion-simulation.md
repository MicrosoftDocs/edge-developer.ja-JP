---
title: Microsoft Edge DevTools を配色のプレビューモードに強制する (CSS は配色パターンを優先)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 94c5369f0eb35059933be7f6202a4f64450629cd
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758111"
---
# モーションシミュレーションの減少  

Web 製品のアニメーションには、アクセシビリティの問題がある可能性があります。  オペレーティングシステムは、アニメーションをオフにするオプションを含めることで問題を解決します。これにより、ユーザーの混乱と、発作のトリガーなどの正常性関連の問題を回避することができます。  Web では、ユーザーがアニメーションを表示しないようにしているかどうかを検出するために、[アニメーションの[優先][MDNPrefersReducedMotion]] という CSS メディアクエリを使用することができます。  製品では、アニメーションコードをテストにラップして、影響を受けるユーザーに対してアニメーションが表示されないようにすることができます。  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
  animation: none;
  }
}
```  

[Microsoft Edge DevTools][DevtoolsGuideChromiumMain]を使うと、オペレーティングシステムを変更せずに、このようなアニメーション設定をシミュレートすることができます。  

1.  **コマンドメニュー**を開きます。  
    1.  `Control` + `Shift` + `P` Windows または macOS を押し `Command` + `Shift` + `P` ます。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **コマンドメニュー**  
        :::image-end:::   
        
1.  「 `reduced` 」と入力してシミュレーションのオンとオフを切り替えます。  オプションを選択して、キーを押し `Enter` ます。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="コマンドメニューの [アニメーションの優先設定] の設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       **コマンドメニュー**の [**アニメーションの優先**設定] の設定をオンまたはオフにする  
    :::image-end:::  
    
1.  現在のページを更新して、アニメーションがオフになっているか表示されているかをテストします。  
    
<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "図 1: コマンドメニュー"  
[ImageToggleReducedMotionFromCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png "図 2: コマンドパレットからのアニメーションの軽減"

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール Microsoft |Microsoft ドキュメント"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion "低優先-モーション |MDN"  