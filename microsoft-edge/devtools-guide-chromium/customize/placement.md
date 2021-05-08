---
description: DevTools Microsoft Edgeビューポートの下部または左側、または別のウィンドウに移動する方法。
title: DevTools Microsoft Edgeを変更する (Undock、Dock to bottom、Dock to left)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c4aca068c159f03b60bbf6d7643bb334a5b5a7f2
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519157"
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

# <a name="change-microsoft-edge-devtools-placement-undock-dock-to-bottom-dock-to-left"></a>DevTools Microsoft Edgeを変更する (Undock、Dock to bottom、Dock to left)  

既定では、DevTools はビューポート (ウィンドウ) の右側にドッキングされます。  また、DevTools をウィンドウの下部または左側にドッキングしたり、DevTools を別のウィンドウにドッキング解除したりすることもできます。

:::row:::
   :::column span="":::
      DevTools はウィンドウの左側にドッキングされています。
   :::column-end:::
   :::column span="":::
      DevTools はウィンドウの下部にドッキングされています。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="[左へドック] を選択する" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         [左 **へドック] を選択する**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="[下へドッキング] を選択する" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         選択 `Dock to bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

DevTools は別のウィンドウにドッキング解除され、別のモニターに移動できます。

:::row:::
   :::column span="":::
      ブラウザー ウィンドウ:
   :::column-end:::
   :::column span="":::
      DevTools は、別のウィンドウでドッキング解除されます。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="別のウィンドウのブラウザー" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         別のウィンドウのブラウザー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="別のウィンドウでドッキングされていない DevTools" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         別のウィンドウでドッキングされていない DevTools  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="change-placement-from-the-main-menu"></a>メイン メニューから配置を変更する  

1.  **[DevTools** \( \) をカスタマイズして制御する] を選択し、[別のウィンドウ `...` \( Undock \), Dock **** to bottom \( Dock to bottom \), または Dock to left \( Dock to ![ ](../media/undock-icon.msft.png) left **** ![ ](../media/bottom-icon.msft.png) **** ![ ](../media/left-icon.msft.png) \) を選択します。  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="[別のウィンドウにドッキング解除] を選択する" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       [別 **のウィンドウにドッキングを解除する] を選択する**  
    :::image-end:::  
    
## <a name="change-placement-from-the-command-menu"></a>コマンド メニューから配置を変更する  

1.  [コマンド メニューを開き][DevtoolsCommandMenu] `Shift` + `Ctrl` + `P` 、Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。  
1.  文字の `>` 後に、 `dock` と入力し、次のいずれかのコマンドを選択します。  
    
    *  **下にドッキングする**
    *  **左にドッキングする**
    *  **右にドッキングする**
    *  **最後のドック位置を復元する**
    *  **別のウィンドウへのドッキングを解除する**
    
    メイン メニューからコマンドに [アクセスすることもできます](#change-placement-from-the-main-menu)。 
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="[元に戻す] コマンド" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       [元に戻す] コマンド  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "[DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/customize/placement) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
