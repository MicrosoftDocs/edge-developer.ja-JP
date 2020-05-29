---
title: Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f0be6243d4780e4ed49428ebaf2b6b37d9da323e
ms.sourcegitcommit: 67ce64f810afdb304844bae0f3918d4e9108dcec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "10601347"
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

> ##### 図 1  
> 左へのドッキング  
> ![左へのドッキング][ImageDockLeft]  

> ##### 図 2  
> 下に固定  
> ![下に固定][ImageDockBottom]  

> ##### 図 3  
> 別のウィンドウに表示されるブラウザー  
> ![別のウィンドウに表示されるブラウザー][ImageUndockBrowser]  

> ##### 図 4  
> 独立したウィンドウに表示されるアンドックされる DevTools  
> ![独立したウィンドウに表示されるアンドックされる DevTools][ImageUndockDevTools]  

## メインメニューから配置を変更する   

1.  [**コントロールのカスタマイズと制御**] をクリックして、[ウィンドウの固定を解除]、[下へドッキング]、[左へ] の順に `...` 選択し**Undock Into Separate Window** ![ ][ImageUndockIcon] **Dock To Bottom** ![ ][ImageBottomIcon] **Dock To Left** ![ ][ImageLeftIcon] ます。  
    
    > ##### 図 5  
    > [**別のウィンドウにドッキングを解除する] を**選ぶ  
    > ![[別のウィンドウにドッキングを解除する] を選ぶ][ImageUndockSettings]  
    
## コマンドメニューから配置を変更する   

1.  [コマンドメニューを開き][DevtoolsCommandMenu]ます。  
1.  次のいずれかのコマンド `Dock To Bottom` を実行 `Undock Into Separate Window` します。  現時点では、左へのドッキング用のコマンドはありませんが、[メインメニュー](#change-placement-from-the-main-menu)からアクセスできます。  
    
    > ##### 図 6  
    > [ドッキング解除] コマンド  
    > ![[ドッキング解除] コマンド][ImageUndockCommand]  

 



<!-- image links -->  

[ImageUndockIcon]: /microsoft-edge/devtools-guide-chromium/media/undock-icon.msft.png  
[ImageBottomIcon]: /microsoft-edge/devtools-guide-chromium/media/bottom-icon.msft.png  
[ImageLeftIcon]: /microsoft-edge/devtools-guide-chromium/media/left-icon.msft.png  

[ImageDockLeft]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-right-docked.msft.png "図 1: 左へのドッキング"  
[ImageDockBottom]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-bottom-docked.msft.png "図 2: 下へのドッキング"  
[ImageUndockBrowser]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight-browser.msft.png "図 3: 別のウィンドウに表示されるブラウザー"  
[ImageUndockDevTools]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png "図 4: 別のウィンドウに表示されるアンドックされる DevTools"  
[ImageUndockSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight.msft.png "図 5: 別のウィンドウにドッキングを解除する"  
[ImageUndockCommand]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-command-menu-undo.msft.png "図 6: [ドッキング解除] コマンド"  

<!-- links -->  

[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/customize/placement)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
