---
title: Microsoft Edge DevTools で位置情報を上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 307064bedf992e528b6d79eed3a2ade3367830d4
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607441"
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





# Microsoft Edge DevTools で位置情報を上書きする   



多くの web サイトでは、ユーザーにより関連性の高いエクスペリエンスを提供するために、ユーザーの位置情報を利用しています。  たとえば、天気予報の web サイトでは、ユーザーが現在のユーザーの場所にアクセスするためのアクセス許可を付与した後、そのユーザーの領域にローカルの予測が表示される場合があります。  

<!--todo: add link to user location section when available -->  

ユーザーがどこにいるかによって変更される UI を作成する場合は、サイトが世界のさまざまな場所で適切に動作することを確認する必要があります。  Microsoft Edge DevTools で位置情報を上書きするには、次の操作を行います。  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。  
    
    > ##### 図 1  
    > コマンドメニュー  
    > ![コマンドメニュー][ImageCommandMenu]  
    
1.  「」と入力して、「 `sensors` **センサーを表示**」を選択し、を押し `Enter` ます。  [**センサー** ] タブが、[devtools] ウィンドウの下部に表示されます。  
1.  [位置**情報] リストから**、いずれかの事前設定された都市のいずれかを選択するか、[ `Tokyo` カスタムの**場所**] を選択してカスタムの経度と緯度の座標を入力するか、[場所を選択**でき**ません] を選択してユーザーの位置情報が表示されない場合の動作を確認します。  
    
    > ##### 図 2  
    > `Tokyo`**位置**情報リストからの選択  
    > ![位置情報リストから東京を選ぶ][ImageGeolocationTokyo]  
    
<!--## Feedback   

  -->  

<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-command-menu.msft.png "図 1: コマンドメニュー"  
[ImageGeolocationTokyo]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-sensors-geolocation-tokyo.msft.png "図 2: 位置情報リストから東京を選ぶ"  

<!-- links -->  

<!--[WebFundamentalsNativeHardwareUserLocationIndex]: /web/fundamentals/native-hardware/user-location/index "User Location"  -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
