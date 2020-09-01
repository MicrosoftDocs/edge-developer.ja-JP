---
title: Microsoft Edge DevTools を使ってデバイスの向きをシミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c9a2aecfff1101de532eb59f73da21a32d62c791
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985015"
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





# <span data-ttu-id="8f179-103">Microsoft Edge DevTools を使ってデバイスの向きをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="8f179-103">Simulate device orientation with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="8f179-104">Microsoft Edge DevTools からさまざまなデバイスの向きをシミュレートするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8f179-104">To simulate different device orientations from Microsoft Edge DevTools:</span></span>  

<!--todo: update device orientation section when available -->  

1.  <span data-ttu-id="8f179-105">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="8f179-105">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="8f179-107">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="8f179-107">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8f179-108">「」と入力して、「 `sensors` **センサーを表示**」を選択し、を押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="8f179-108">Type `sensors`, select **Show Sensors**, and press `Enter`.</span></span>  <span data-ttu-id="8f179-109">[ **センサー** ] タブが、[devtools] ウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f179-109">The **Sensors** tab opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="8f179-110">[**印刷の向き**] ボックスの一覧で、[などの事前設定の向き] のいずれかを選択するか、独自の向きを選択して、 `Portrait upside down` 正確な向きを指定します。 **Custom orientation**</span><span class="sxs-lookup"><span data-stu-id="8f179-110">From the **Orientation** list, select one of the preset orientations, such as `Portrait upside down`, or select **Custom orientation** to provide your own exact orientation.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png" alt-text="[向き] の一覧から [縦] を上下に反転する" lightbox="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png":::
             <span data-ttu-id="8f179-112">[ `Portrait upside down` 印刷の **向き** ] の一覧から選択する</span><span class="sxs-lookup"><span data-stu-id="8f179-112">Select `Portrait upside down` from the **Orientation** list</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="8f179-113">[ **ユーザー設定の向き**] を選択すると、、、 `alpha` `beta` および `gamma` フィールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="8f179-113">After you select **Custom orientation**, the `alpha`, `beta`, and `gamma` fields are enabled.</span></span>  
          <!--See [Alpha][alpha], [Beta][beta], and [Gamma][gamma] to understand how these axes work.  -->  
          <!--todo: update links to alpha, beta, and gamma section when available -->  
          <span data-ttu-id="8f179-114">**向きのモデル**をドラッグして、独自の向きを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f179-114">You are also able to set a custom orientation by dragging the **Orientation Model**.</span></span>  <span data-ttu-id="8f179-115">`Shift`ドラッグして軸に沿って回転させ `alpha` ます。</span><span class="sxs-lookup"><span data-stu-id="8f179-115">Hold `Shift` before dragging to rotate along the `alpha` axis.</span></span>  
          
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-custom.msft.png" alt-text="向きのモデル" lightbox="../media/device-mode-console-sensors-orientation-custom.msft.png":::
             <span data-ttu-id="8f179-117">**向きのモデル**</span><span class="sxs-lookup"><span data-stu-id="8f179-117">The **Orientation Model**</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
<!--  
## Feedback 


-->  

<!-- links -->  

<!--[WebFundamentasNativeHardwareDeviceOrientationIndex]: /web/fundamentals/native-hardware/device-orientation/index "Device Orientation \& Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexAlpha]: /web/fundamentals/native-hardware/device-orientation/index#alpha "Alpha - Device Orientation \& Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexBeta]: /web/fundamentals/native-hardware/device-orientation/index#beta "Beta - Device Orientation \& Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexGamma]: /web/fundamentals/native-hardware/device-orientation/index#gamma "Gamma - Device Orientation \& Motion"  -->  

> [!NOTE]
> <span data-ttu-id="8f179-118">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f179-118">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8f179-119">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="8f179-119">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="8f179-121">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="8f179-121">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
