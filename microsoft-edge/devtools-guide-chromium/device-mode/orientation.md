---
title: Microsoft Edge DevTools を使ってデバイスの向きをシミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e11af27681f3aa1aaeefb62505908fdc6cd7a0e9
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986151"
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

# Microsoft Edge DevTools を使ってデバイスの向きをシミュレートする  

Microsoft Edge DevTools からさまざまなデバイスの向きをシミュレートするには、次の操作を実行します。  

<!--todo: update device orientation section when available -->  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       **コマンドメニュー**  
    :::image-end:::  
    
1.  「」と入力して、「 `sensors` **センサーを表示**」を選択し、を押し `Enter` ます。  [ **センサー** ] タブが、[devtools] ウィンドウの下部に表示されます。  
1.  [**印刷の向き**] ボックスの一覧で、[などの事前設定の向き] のいずれかを選択するか、独自の向きを選択して、 `Portrait upside down` 正確な向きを指定します。 **Custom orientation**  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png" alt-text="[向き] の一覧から [縦] を上下に反転する" lightbox="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png":::
             [ `Portrait upside down` 印刷の **向き** ] の一覧から選択する  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          [ **ユーザー設定の向き**] を選択すると、、、 `alpha` `beta` および `gamma` フィールドが有効になります。  
          <!--See [Alpha][alpha], [Beta][beta], and [Gamma][gamma] to understand how each axis works.  -->  
          <!--todo: update links to alpha, beta, and gamma section when available -->  
          **向きのモデル**をドラッグして、独自の向きを設定することもできます。  `Shift`ドラッグして軸に沿って回転させ `alpha` ます。  
          
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-custom.msft.png" alt-text="向きのモデル" lightbox="../media/device-mode-console-sensors-orientation-custom.msft.png":::
             **向きのモデル**  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## Microsoft Edge DevTools チームと連絡を取り合う  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentasNativeHardwareDeviceOrientationIndex]: /web/fundamentals/native-hardware/device-orientation/index "Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexAlpha]: /web/fundamentals/native-hardware/device-orientation/index#alpha "Alpha - Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexBeta]: /web/fundamentals/native-hardware/device-orientation/index#beta "Beta - Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexGamma]: /web/fundamentals/native-hardware/device-orientation/index#gamma "Gamma - Device Orientation & Motion"  -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
