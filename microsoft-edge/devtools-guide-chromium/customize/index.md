---
title: Microsoft Edge DevTools をカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 42c1cce2ca26c81b0482429cface83f09e34f5df
ms.sourcegitcommit: 67ce64f810afdb304844bae0f3918d4e9108dcec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "10601354"
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





# Microsoft Edge DevTools をカスタマイズする   

  

このページでは、Microsoft Edge DevTools をカスタマイズする方法を示します。  

## 設定   

**設定**  > **環境設定**には、devtools をカスタマイズするための多くのオプションが含まれています。  

[設定] を開くには、次のいずれかの操作を行います。  

*   `F1`DevTools がフォーカスされているときに、を押します。  
*   **メインメニュー**を開き、[**設定**] を選択します。  

> ##### 図 1  
> 設定  
> ![設定][ImageSettings]  

## ドロアー   

**ドロワー**には、多くの非表示機能が含まれています。  

を押して `Escape` 、引き出しを開くか、閉じます。  

> ##### 図 2  
> ドロワー  
> ![ドロワー][ImageDrawerExample]  

[**その他]** をクリックして ![ ][ImageMoreIcon] 、他の引き出しタブを開きます。  

> ##### 図 3  
> 引き出しタブを開くためのボタン  
> ![引き出しタブを開くためのボタン][ImageMoreDrawerTabs]  

## パネルの順序を変更する   

パネルタブをクリックし、ドラッグして順序を変更します。  カスタムタブの順序は、DevTools セッション間で維持されます。  

> [!NOTE]
> 既定では、[ネットワークパネル] タブは左側の4番目のタブにあります。  [図 4](#figure-4)では、左側の最初のものです。  

> ##### 図 4  
> カスタムタブオーダーが表示された DevTools ウィンドウ    
> ![カスタムパネルタブの順序が表示された DevTools ウィンドウ][ImageCustomTabOrdering]  

## DevTools の配置を変更する   

「 [Microsoft Edge DevTools の配置][DevToolsPlacement]」を参照してください。  

> ##### 図 5  
> アンドックした DevTools  
> ![アンドックした DevTools][ImageUndock]  

## 濃色テーマ   

「[濃色テーマを有効にする」を][DarkTheme]参照してください。  

> ##### 図 6  
> 濃色テーマ  
> ![濃色テーマ][ImageDarkTheme]  

## テスト   

DevTools の実験を有効にするには:  

1.  に移動 `edge://flags/#enable-devtools-experiments` します。  
1.  **[有効]** をクリックします。  
1.  ページの下部にある [**今すぐ**再起動] をクリックします。  

次に DevTools を開くと、[[設定](#settings)] に "**実験**" という新しいページが表示されます。  

   

  

<!-- image links -->  

[ImageMoreIcon]: /microsoft-edge/devtools-guide-chromium/media/more-icon.msft.png  

[ImageSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-preferences.msft.png "図 1: 設定"  
[ImageDrawerExample]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open.msft.png "図 2: ドロワー"  
[ImageMoreDrawerTabs]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open-more-tools.msft.png "図 3: [引き出し] タブを開くためのボタン"  
[ImageCustomTabOrdering]: /microsoft-edge/devtools-guide-chromium/media/customize-network-first-position.msft.png "図 4: カスタムパネルタブの順序が表示された DevTools ウィンドウ"  
[ImageUndock]: /microsoft-edge/devtools-guide-chromium/media/customize-dev-tools-dock-side.msft.png "図 5: アンドックした DevTools"  
[ImageDarkTheme]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-appearance-theme.msft.png "図 6: 濃色テーマ"  

<!-- links -->  

[DevToolsPlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DarkTheme]: /microsoft-edge/devtools-guide-chromium/customize/dark-theme "Microsoft Edge DevTools でダークテーマを有効にする"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/customize/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
