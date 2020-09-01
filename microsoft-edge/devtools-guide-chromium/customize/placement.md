---
title: Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: aaa6ef03f6abea27c84fb46db3d2a2f0f894339c
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10981935"
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





# Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)   



既定では、DevTools はビューポートの右側にドッキングされます。  また、下部へのドッキング、左へのドッキング、別のウィンドウへの DevTools のドッキング解除を行うこともできます。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="[左へ] を選ぶ" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         選択する `Dock To Left`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="[下へ] を選ぶ" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         選択する `Dock To Bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="別のウィンドウに表示されるブラウザー" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         別のウィンドウに表示されるブラウザー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="独立したウィンドウに表示されるアンドックされる DevTools" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         独立したウィンドウに表示されるアンドックされる DevTools  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## メインメニューから配置を変更する   

1.  [**カスタマイズと制御**] をクリックし `...` ます。 \ (\) [独立した**ウィンドウに**固定する] (ドッキング解除 \)、[下へ固定] \ (下から下へ)、 ![ ][ImageUndockIcon] **Dock To Bottom** ![ ][ImageBottomIcon] または**左に** ![ ][ImageLeftIcon] 固定  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="[別ウィンドウに装着する] を選ぶ" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       [**別ウィンドウに装着する]** を選ぶ  
    :::image-end:::  
    
## コマンドメニューから配置を変更する   

1.  [コマンドメニューを開き][DevtoolsCommandMenu]ます。  
1.  次のいずれかのコマンド `Dock To Bottom` を実行 `Undock Into Separate Window` します。  現時点では、左へのドッキング用のコマンドはありませんが、 [メインメニュー](#change-placement-from-the-main-menu)からアクセスできます。  
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="[ドッキング解除] コマンド" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       [ドッキング解除] コマンド  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageUndockIcon]: ../media/undock-icon.msft.png  
[ImageBottomIcon]: ../media/bottom-icon.msft.png  
[ImageLeftIcon]: ../media/left-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/customize/placement) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
