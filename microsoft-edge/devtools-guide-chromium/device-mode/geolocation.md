---
description: センサー ツールを開き、[位置情報] リストから座標を選択します。
title: Microsoft Edge DevTools を使用して地理位置情報をオーバーライドする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8f6ad09b2f8db110f6743aae32e16cc9b1185400
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399002"
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

# <a name="override-geolocation-with-microsoft-edge-devtools"></a><span data-ttu-id="176bc-104">Microsoft Edge DevTools を使用して地理位置情報をオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="176bc-104">Override geolocation with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="176bc-105">多くの Web サイトは、ユーザーに関連性の高いエクスペリエンスを提供するために、ユーザーの場所を利用します。</span><span class="sxs-lookup"><span data-stu-id="176bc-105">Many websites take advantage of user location in order to provide a more relevant experience for the users.</span></span>  <span data-ttu-id="176bc-106">たとえば、天気予報 Web サイトでは、ユーザーが現在のユーザーの場所にアクセスするためのアクセス許可を Web サイトに付与した後、ユーザーの地域にローカル予測を表示できます。</span><span class="sxs-lookup"><span data-stu-id="176bc-106">For example, a weather website may show the local forecast in a user's area, after the user has granted the website permission to access the current user location.</span></span>  

<!--todo: add link to user location section when available -->  

<span data-ttu-id="176bc-107">ユーザーの場所に応じて変更される UI を構築する場合は、サイトが世界中の異なる場所で正しく動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="176bc-107">If you are building a UI that changes depending on where the user is located, you probably want to make sure that the site behaves correctly in different places around the world.</span></span>  <span data-ttu-id="176bc-108">Microsoft Edge DevTools で位置情報を上書きするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="176bc-108">To override your geolocation in Microsoft Edge DevTools, complete the following actions.</span></span>  

1.  <span data-ttu-id="176bc-109">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="176bc-109">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンド メニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="176bc-111">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="176bc-111">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="176bc-112">[種類 `sensors` ] を選択 **し、[センサーの表示]** を選択し、[ ] を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="176bc-112">Type `sensors`, choose **Show Sensors**, and select `Enter`.</span></span>  <span data-ttu-id="176bc-113">センサー **ツールが** DevTools ウィンドウの下部に開きます。</span><span class="sxs-lookup"><span data-stu-id="176bc-113">The **Sensors** tool opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="176bc-114">[位置情報] リストから、あらかじめ設定されている都市のいずれかを選択するか、[カスタムの場所] を選択してカスタムの経度と緯度の座標を入力するか、[使用できない場所] を選択して、ユーザーの場所が使用できない場合のサイトの動作を表示します。 `Tokyo`  </span><span class="sxs-lookup"><span data-stu-id="176bc-114">From the **Geolocation** list select one of the preset cities, like `Tokyo`, or choose **Custom location** to enter custom longitude and latitude coordinates, or choose **Location unavailable** to display how your site behaves when the user's location is not available.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-sensors-geolocation-tokyo.msft.png" alt-text="地理位置情報リストから東京を選択する" lightbox="../media/device-mode-console-sensors-geolocation-tokyo.msft.png":::
       <span data-ttu-id="176bc-116">位置情報 `Tokyo` リスト **から選択** する</span><span class="sxs-lookup"><span data-stu-id="176bc-116">Choose `Tokyo` from the **Geolocation** list</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="176bc-117">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="176bc-117">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentalsNativeHardwareUserLocationIndex]: /web/fundamentals/native-hardware/user-location/index "User Location"  -->  

> [!NOTE]
> <span data-ttu-id="176bc-118">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="176bc-118">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="176bc-119">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="176bc-119">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="176bc-121">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="176bc-121">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
