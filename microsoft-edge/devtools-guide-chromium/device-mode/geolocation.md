---
description: '[センサー] タブを開き、[位置情報] の一覧から [座標] を選びます。'
title: Microsoft Edge DevTools で位置情報を上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 269e7ca4bf259aa168c06ac0fd915604731463c4
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992989"
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

# <span data-ttu-id="0f462-104">Microsoft Edge DevTools で位置情報を上書きする</span><span class="sxs-lookup"><span data-stu-id="0f462-104">Override geolocation with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="0f462-105">多くの web サイトでは、ユーザーにより関連性の高いエクスペリエンスを提供するために、ユーザーの位置情報を利用しています。</span><span class="sxs-lookup"><span data-stu-id="0f462-105">Many websites take advantage of user location in order to provide a more relevant experience for the users.</span></span>  <span data-ttu-id="0f462-106">たとえば、天気予報の web サイトでは、ユーザーが現在のユーザーの場所にアクセスするためのアクセス許可を付与した後、そのユーザーの領域にローカルの予測が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f462-106">For example, a weather website may show the local forecast in a user's area, after the user has granted the website permission to access the current user location.</span></span>  

<!--todo: add link to user location section when available -->  

<span data-ttu-id="0f462-107">ユーザーがどこにいるかによって変更される UI を作成する場合は、サイトが世界のさまざまな場所で適切に動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f462-107">If you are building a UI that changes depending on where the user is located, you probably want to make sure that the site behaves correctly in different places around the world.</span></span>  <span data-ttu-id="0f462-108">Microsoft Edge DevTools で位置情報を上書きするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f462-108">To override your geolocation in Microsoft Edge DevTools, complete the following actions.</span></span>  

1.  <span data-ttu-id="0f462-109">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="0f462-109">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="0f462-111">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="0f462-111">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0f462-112">「」と入力して、「 `sensors` **センサーを表示**」を選択し、を押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0f462-112">Type `sensors`, select **Show Sensors**, and press `Enter`.</span></span>  <span data-ttu-id="0f462-113">[ **センサー** ] タブが、[devtools] ウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f462-113">The **Sensors** tab opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="0f462-114">[位置 **情報] リストから** 、いずれかの事前設定された都市のいずれかを選択するか、[ `Tokyo` カスタムの **場所** ] を選択してカスタムの経度と緯度の座標を入力するか、[場所を選択 **でき** ません] を選択してユーザーの位置情報が表示されない場合の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f462-114">From the **Geolocation** list select one of the preset cities, like `Tokyo`, or select **Custom location** to enter custom longitude and latitude coordinates, or select **Location unavailable** to see how your site behaves when the user's location is not available.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-sensors-geolocation-tokyo.msft.png" alt-text="位置情報リストから東京を選ぶ" lightbox="../media/device-mode-console-sensors-geolocation-tokyo.msft.png":::
       <span data-ttu-id="0f462-116">`Tokyo`**位置**情報リストから選択する</span><span class="sxs-lookup"><span data-stu-id="0f462-116">Select `Tokyo` from the **Geolocation** list</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0f462-117">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="0f462-117">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentalsNativeHardwareUserLocationIndex]: /web/fundamentals/native-hardware/user-location/index "User Location"  -->  

> [!NOTE]
> <span data-ttu-id="0f462-118">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f462-118">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0f462-119">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="0f462-119">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0f462-121">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0f462-121">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
