---
description: 開発者ツールを使用して、縮小されたモーションをシミュレートします。
title: 開発者ツールを使用して縮小モーションをシミュレートする (CSS Prefers Reduced Motion)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7244c2e80bbf9070214b6abd02583792c785953c
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597058"
---
# <a name="reduced-motion-simulation"></a>モーション シミュレーションの削減  

Web 製品のアニメーションはアクセシビリティの問題である可能性があります。  オペレーティング システムは、ユーザーの混乱や、発作のトリガーなど、潜在的な健康関連の問題を回避するためにアニメーションをオフにするオプションを含めて、この問題に対処します。  

Web ページでは、優先的に縮小された [CSS][MDNPrefersReducedMotion] メディア クエリを使用して、ユーザーがアニメーションを表示することを好むかどうかを検出できます。  次に、テストでアニメーション コードをラップし、条件付きでアニメーションを実行します。  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

次に、次のようにコードをテストします。

オペレーティング システムの設定を変更せずに、オペレーティング システムの縮小モーション設定をシミュレートするには、次の操作を行います。

1.  **コマンド メニュー** を開きます。  
    1.  `Control` + `Shift` + `P` [Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **コマンド メニュー**  
        :::image-end:::  
        
1.  `reduced`「」と入力して、シミュレーションのオンとオフを切り替えます。  オプションを選択して選択します `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="[コマンド メニュー] から低いモーション設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       [コマンド メニュー] から低い **モーション設定をオン** または **オフにする**  
    :::image-end:::  
    
1.  Web ページを更新し、アニメーションが実行されているかどうかを確認します。


## <a name="see-also"></a>関連項目

* [UI アニメーションをオフに](test-reduced-ui-motion.md) した状態でページが使用可能になっていることを確認する - 説明付きデモ ページを使用したチュートリアル。

    
<!-- links -->  
[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "縮小モーション を優先|MDN"  
