---
description: センサー ツールを開き、[方向] セクションに移動します。
title: DevTools を使用してデバイスMicrosoft Edgeシミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 71527d8dce0d7a0563feef0081ce12d40eeb5e1a
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564309"
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
# <a name="simulate-device-orientation-with-microsoft-edge-devtools"></a>DevTools を使用してデバイスMicrosoft Edgeシミュレートする  

DevTools からさまざまなデバイスの向きをシミュレートするには、次Microsoft Edge実行します。  

<!--todo: update device orientation section when available -->  

1.  `Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンド メニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  [種類 `sensors` ] を選択 **し、[センサーの表示]** を選択し、[ ] を選択します `Enter` 。  センサー **ツールが** DevTools ウィンドウの下部に開きます。  
1.  [方向 **] ボックスの**一覧から、プリセットの向き (など) のいずれかを選択するか、[カスタムの向き] を選択して、独自の正確な方向 `Portrait upside down` **** を指定します。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png" alt-text="[向き] リストから [縦向き] を逆さまに選択する" lightbox="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png":::
             [方向 `Portrait upside down` ] リスト **から選択** する  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          [ユーザー設定の **向き] を選択**すると `alpha` 、、 `beta` 、および `gamma` フィールドが有効になります。  
          <!--To understand how each axis works, navigate to [Alpha][alpha], [Beta][beta], and [Gamma][gamma].  -->  
          <!--todo: update links to alpha, beta, and gamma section when available -->  
          また、方向モデルをドラッグしてカスタムの向きを **設定できます**。  軸 `Shift` に沿って回転するには、ドラッグする前に保持 `alpha` します。  
          
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-custom.msft.png" alt-text="方向モデル" lightbox="../media/device-mode-console-sensors-orientation-custom.msft.png":::
             方向 **モデル**  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentasNativeHardwareDeviceOrientationIndex]: /web/fundamentals/native-hardware/device-orientation/index "Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexAlpha]: /web/fundamentals/native-hardware/device-orientation/index#alpha "Alpha - Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexBeta]: /web/fundamentals/native-hardware/device-orientation/index#beta "Beta - Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexGamma]: /web/fundamentals/native-hardware/device-orientation/index#gamma "Gamma - Device Orientation & Motion"  -->  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
