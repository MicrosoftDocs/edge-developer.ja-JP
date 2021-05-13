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
# <a name="simulate-device-orientation-with-microsoft-edge-devtools"></a><span data-ttu-id="6ba27-104">DevTools を使用してデバイスMicrosoft Edgeシミュレートする</span><span class="sxs-lookup"><span data-stu-id="6ba27-104">Simulate device orientation with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="6ba27-105">DevTools からさまざまなデバイスの向きをシミュレートするには、次Microsoft Edge実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba27-105">Complete the following actions to simulate different device orientations from Microsoft Edge DevTools.</span></span>  

<!--todo: update device orientation section when available -->  

1.  <span data-ttu-id="6ba27-106">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba27-106">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンド メニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="6ba27-108">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="6ba27-108">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6ba27-109">[種類 `sensors` ] を選択 **し、[センサーの表示]** を選択し、[ ] を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="6ba27-109">Type `sensors`, choose **Show Sensors**, and select `Enter`.</span></span>  <span data-ttu-id="6ba27-110">センサー **ツールが** DevTools ウィンドウの下部に開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba27-110">The **Sensors** tool opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="6ba27-111">[方向 **] ボックスの**一覧から、プリセットの向き (など) のいずれかを選択するか、[カスタムの向き] を選択して、独自の正確な方向 `Portrait upside down` \*\*\*\* を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ba27-111">From the **Orientation** list, select one of the preset orientations, such as `Portrait upside down`, or choose **Custom orientation** to provide your own exact orientation.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png" alt-text="[向き] リストから [縦向き] を逆さまに選択する" lightbox="../media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png":::
             <span data-ttu-id="6ba27-113">[方向 `Portrait upside down` ] リスト **から選択** する</span><span class="sxs-lookup"><span data-stu-id="6ba27-113">Choose `Portrait upside down` from the **Orientation** list</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="6ba27-114">[ユーザー設定の **向き] を選択**すると `alpha` 、、 `beta` 、および `gamma` フィールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ba27-114">After you choose **Custom orientation**, the `alpha`, `beta`, and `gamma` fields are enabled.</span></span>  
          <!--To understand how each axis works, navigate to [Alpha][alpha], [Beta][beta], and [Gamma][gamma].  -->  
          <!--todo: update links to alpha, beta, and gamma section when available -->  
          <span data-ttu-id="6ba27-115">また、方向モデルをドラッグしてカスタムの向きを **設定できます**。</span><span class="sxs-lookup"><span data-stu-id="6ba27-115">You are also able to set a custom orientation by dragging the **Orientation Model**.</span></span>  <span data-ttu-id="6ba27-116">軸 `Shift` に沿って回転するには、ドラッグする前に保持 `alpha` します。</span><span class="sxs-lookup"><span data-stu-id="6ba27-116">Hold `Shift` before dragging to rotate along the `alpha` axis.</span></span>  
          
          :::image type="complex" source="../media/device-mode-console-sensors-orientation-custom.msft.png" alt-text="方向モデル" lightbox="../media/device-mode-console-sensors-orientation-custom.msft.png":::
             <span data-ttu-id="6ba27-118">方向 **モデル**</span><span class="sxs-lookup"><span data-stu-id="6ba27-118">The **Orientation Model**</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6ba27-119">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6ba27-119">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentasNativeHardwareDeviceOrientationIndex]: /web/fundamentals/native-hardware/device-orientation/index "Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexAlpha]: /web/fundamentals/native-hardware/device-orientation/index#alpha "Alpha - Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexBeta]: /web/fundamentals/native-hardware/device-orientation/index#beta "Beta - Device Orientation & Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexGamma]: /web/fundamentals/native-hardware/device-orientation/index#gamma "Gamma - Device Orientation & Motion"  -->  

> [!NOTE]
> <span data-ttu-id="6ba27-120">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba27-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6ba27-121">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="6ba27-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6ba27-123">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6ba27-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
