---
title: Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f0be6243d4780e4ed49428ebaf2b6b37d9da323e
ms.sourcegitcommit: 67ce64f810afdb304844bae0f3918d4e9108dcec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "10601347"
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





# <span data-ttu-id="0a236-103">Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)</span><span class="sxs-lookup"><span data-stu-id="0a236-103">Change Microsoft Edge DevTools Placement (Undock, Dock To Bottom, Dock To Left)</span></span>   



<span data-ttu-id="0a236-104">既定では、DevTools はビューポートの右側にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="0a236-104">By default DevTools is docked to the right of your viewport.</span></span>  <span data-ttu-id="0a236-105">また、下部へのドッキング、左へのドッキング、別のウィンドウへの DevTools のドッキング解除を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="0a236-105">You may also dock to bottom, dock to left, or undock the DevTools to a separate window.</span></span>  

> ##### <span data-ttu-id="0a236-106">図 1</span><span class="sxs-lookup"><span data-stu-id="0a236-106">Figure 1</span></span>  
> <span data-ttu-id="0a236-107">左へのドッキング</span><span class="sxs-lookup"><span data-stu-id="0a236-107">Dock To Left</span></span>  
> ![左へのドッキング][ImageDockLeft]  

> ##### <span data-ttu-id="0a236-109">図 2</span><span class="sxs-lookup"><span data-stu-id="0a236-109">Figure 2</span></span>  
> <span data-ttu-id="0a236-110">下に固定</span><span class="sxs-lookup"><span data-stu-id="0a236-110">Dock To Bottom</span></span>  
> ![下に固定][ImageDockBottom]  

> ##### <span data-ttu-id="0a236-112">図 3</span><span class="sxs-lookup"><span data-stu-id="0a236-112">Figure 3</span></span>  
> <span data-ttu-id="0a236-113">別のウィンドウに表示されるブラウザー</span><span class="sxs-lookup"><span data-stu-id="0a236-113">Browser in separate window</span></span>  
> ![別のウィンドウに表示されるブラウザー][ImageUndockBrowser]  

> ##### <span data-ttu-id="0a236-115">図 4</span><span class="sxs-lookup"><span data-stu-id="0a236-115">Figure 4</span></span>  
> <span data-ttu-id="0a236-116">独立したウィンドウに表示されるアンドックされる DevTools</span><span class="sxs-lookup"><span data-stu-id="0a236-116">Undocked DevTools in separate window</span></span>  
> ![独立したウィンドウに表示されるアンドックされる DevTools][ImageUndockDevTools]  

## <span data-ttu-id="0a236-118">メインメニューから配置を変更する</span><span class="sxs-lookup"><span data-stu-id="0a236-118">Change placement from the main menu</span></span>   

1.  <span data-ttu-id="0a236-119">[**コントロールのカスタマイズと制御**] をクリックして、[ウィンドウの固定を解除]、[下へドッキング]、[左へ] の順に `...` 選択し**Undock Into Separate Window** ![ ][ImageUndockIcon] **Dock To Bottom** ![ ][ImageBottomIcon] **Dock To Left** ![ ][ImageLeftIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0a236-119">Click **Customize And Control DevTools** `...` and select **Undock Into Separate Window** ![Undock][ImageUndockIcon], **Dock To Bottom** ![Dock To Bottom][ImageBottomIcon], or **Dock To Left** ![Dock To Left][ImageLeftIcon].</span></span>  
    
    > ##### <span data-ttu-id="0a236-120">図 5</span><span class="sxs-lookup"><span data-stu-id="0a236-120">Figure 5</span></span>  
    > <span data-ttu-id="0a236-121">[**別のウィンドウにドッキングを解除する] を**選ぶ</span><span class="sxs-lookup"><span data-stu-id="0a236-121">Selecting **Undock Into Separate Window**</span></span>  
    > ![[別のウィンドウにドッキングを解除する] を選ぶ][ImageUndockSettings]  
    
## <span data-ttu-id="0a236-123">コマンドメニューから配置を変更する</span><span class="sxs-lookup"><span data-stu-id="0a236-123">Change placement from the Command Menu</span></span>   

1.  <span data-ttu-id="0a236-124">[コマンドメニューを開き][DevtoolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="0a236-124">[Open the Command Menu][DevtoolsCommandMenu].</span></span>  
1.  <span data-ttu-id="0a236-125">次のいずれかのコマンド `Dock To Bottom` を実行 `Undock Into Separate Window` します。</span><span class="sxs-lookup"><span data-stu-id="0a236-125">Run one of the following commands: `Dock To Bottom`, `Undock Into Separate Window`.</span></span>  <span data-ttu-id="0a236-126">現時点では、左へのドッキング用のコマンドはありませんが、[メインメニュー](#change-placement-from-the-main-menu)からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0a236-126">Currently there is no command for docking to left, but you may access it from the [main menu](#change-placement-from-the-main-menu).</span></span>  
    
    > ##### <span data-ttu-id="0a236-127">図 6</span><span class="sxs-lookup"><span data-stu-id="0a236-127">Figure 6</span></span>  
    > <span data-ttu-id="0a236-128">[ドッキング解除] コマンド</span><span class="sxs-lookup"><span data-stu-id="0a236-128">The undock command</span></span>  
    > ![[ドッキング解除] コマンド][ImageUndockCommand]  

 



<!-- image links -->  

[ImageUndockIcon]: /microsoft-edge/devtools-guide-chromium/media/undock-icon.msft.png  
[ImageBottomIcon]: /microsoft-edge/devtools-guide-chromium/media/bottom-icon.msft.png  
[ImageLeftIcon]: /microsoft-edge/devtools-guide-chromium/media/left-icon.msft.png  

[ImageDockLeft]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-right-docked.msft.png "図 1: 左へのドッキング"  
[ImageDockBottom]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-bottom-docked.msft.png "図 2: 下へのドッキング"  
[ImageUndockBrowser]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight-browser.msft.png "図 3: 別のウィンドウに表示されるブラウザー"  
[ImageUndockDevTools]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png "図 4: 別のウィンドウに表示されるアンドックされる DevTools"  
[ImageUndockSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight.msft.png "図 5: 別のウィンドウにドッキングを解除する"  
[ImageUndockCommand]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-command-menu-undo.msft.png "図 6: [ドッキング解除] コマンド"  

<!-- links -->  

[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  

> [!NOTE]
> <span data-ttu-id="0a236-137">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a236-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0a236-138">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/customize/placement)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="0a236-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/placement) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0a236-140">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0a236-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
