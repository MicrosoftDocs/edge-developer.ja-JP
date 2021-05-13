---
description: センサー ツールを開き、[位置情報] リストから座標を選択します。
title: DevTools で地理Microsoft Edgeオーバーライドする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5e162d5591dec4013a899a16b0c56fd09d58610f
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564330"
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
# <a name="override-geolocation-with-microsoft-edge-devtools"></a>DevTools で地理Microsoft Edgeオーバーライドする  

多くの Web サイトは、ユーザーに関連性の高いエクスペリエンスを提供するために、ユーザーの場所を利用します。  たとえば、天気予報 Web サイトでは、ユーザーが現在のユーザーの場所にアクセスするためのアクセス許可を Web サイトに付与した後、ユーザーの地域にローカル予測を表示できます。  

<!--todo: add link to user location section when available -->  

ユーザーの場所に応じて変更される UI を構築する場合は、サイトが世界中の異なる場所で正しく動作することを確認する必要があります。  DevTools で位置情報をMicrosoft Edgeするには、次の操作を実行します。  

1.  `Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンド メニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  [種類 `sensors` ] を選択 **し、[センサーの表示]** を選択し、[ ] を選択します `Enter` 。  センサー **ツールが** DevTools ウィンドウの下部に開きます。  
1.  [位置情報****] リストから、あらかじめ設定されている都市のいずれかを選択するか、[カスタムの場所] を選択してカスタムの経度と緯度の座標を入力するか、[使用できない場所] を選択して、ユーザーの場所が使用できない場合のサイトの動作を表示します。 `Tokyo` **** ****  
    
    :::image type="complex" source="../media/device-mode-console-sensors-geolocation-tokyo.msft.png" alt-text="地理位置情報リストから東京を選択する" lightbox="../media/device-mode-console-sensors-geolocation-tokyo.msft.png":::
       位置情報 `Tokyo` リスト **から選択** する  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentalsNativeHardwareUserLocationIndex]: /web/fundamentals/native-hardware/user-location/index "User Location"  -->  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
