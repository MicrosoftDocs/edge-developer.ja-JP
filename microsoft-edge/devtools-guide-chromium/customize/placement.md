---
description: Microsoft Edge DevTools をビューポートの下部または左側、または別のウィンドウに移動する方法。
title: Microsoft Edge DevTools の配置を変更する (Undock、Dock to bottom、Dock to left)
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

# <a name="change-microsoft-edge-devtools-placement-undock-dock-to-bottom-dock-to-left"></a><span data-ttu-id="4027d-104">Microsoft Edge DevTools の配置を変更する (Undock、Dock to bottom、Dock to left)</span><span class="sxs-lookup"><span data-stu-id="4027d-104">Change Microsoft Edge DevTools placement (Undock, Dock to bottom, Dock to left)</span></span>  

<span data-ttu-id="4027d-105">既定では、DevTools はビューポート (ウィンドウ) の右側にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="4027d-105">By default, DevTools is docked to the right of your viewport (window).</span></span>  <span data-ttu-id="4027d-106">また、DevTools をウィンドウの下部または左側にドッキングしたり、DevTools を別のウィンドウにドッキング解除したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4027d-106">You may also dock DevTools to the bottom or left of the window, or undock DevTools to a separate window.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="4027d-107">DevTools はウィンドウの左側にドッキングされています。</span><span class="sxs-lookup"><span data-stu-id="4027d-107">DevTools docked to the left side of the window:</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="4027d-108">DevTools はウィンドウの下部にドッキングされています。</span><span class="sxs-lookup"><span data-stu-id="4027d-108">DevTools docked to the bottom of the window:</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="[左へドック] を選択する" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         <span data-ttu-id="4027d-110">[左 **へドック] を選択する**</span><span class="sxs-lookup"><span data-stu-id="4027d-110">Choose **Dock to left**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="[下へドッキング] を選択する" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         <span data-ttu-id="4027d-112">選択</span><span class="sxs-lookup"><span data-stu-id="4027d-112">Choose</span></span> `Dock to bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="4027d-113">DevTools は別のウィンドウにドッキング解除され、別のモニターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="4027d-113">DevTools may be undocked to a separate window, which you may move to a separate monitor:</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="4027d-114">ブラウザー ウィンドウ:</span><span class="sxs-lookup"><span data-stu-id="4027d-114">Browser window:</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="4027d-115">DevTools は、別のウィンドウでドッキング解除されます。</span><span class="sxs-lookup"><span data-stu-id="4027d-115">DevTools undocked in a separate window:</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="別のウィンドウのブラウザー" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         <span data-ttu-id="4027d-117">別のウィンドウのブラウザー</span><span class="sxs-lookup"><span data-stu-id="4027d-117">Browser in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="別のウィンドウでドッキングされていない DevTools" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         <span data-ttu-id="4027d-119">別のウィンドウでドッキングされていない DevTools</span><span class="sxs-lookup"><span data-stu-id="4027d-119">Undocked DevTools in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="change-placement-from-the-main-menu"></a><span data-ttu-id="4027d-120">メイン メニューから配置を変更する</span><span class="sxs-lookup"><span data-stu-id="4027d-120">Change placement from the main menu</span></span>  

1.  <span data-ttu-id="4027d-121">**[DevTools** \( \) をカスタマイズして制御する] を選択し、[別のウィンドウ `...` \( Undock \), Dock \*\*\*\* to bottom \( Dock to bottom \), または Dock to left \( Dock to ![ ](../media/undock-icon.msft.png) left \*\*\*\* ![ ](../media/bottom-icon.msft.png) \*\*\*\* ![ ](../media/left-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4027d-121">Choose **Customize and control DevTools** \(`...`\) and choose **Undock into separate window** \(![Undock](../media/undock-icon.msft.png)\), **Dock to bottom** \(![Dock to bottom](../media/bottom-icon.msft.png)\), or **Dock to left** \(![Dock to left](../media/left-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="[別のウィンドウにドッキング解除] を選択する" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       <span data-ttu-id="4027d-123">[別 **のウィンドウにドッキングを解除する] を選択する**</span><span class="sxs-lookup"><span data-stu-id="4027d-123">Choose **Undock into separate window**</span></span>  
    :::image-end:::  
    
## <a name="change-placement-from-the-command-menu"></a><span data-ttu-id="4027d-124">コマンド メニューから配置を変更する</span><span class="sxs-lookup"><span data-stu-id="4027d-124">Change placement from the Command Menu</span></span>  

1.  <span data-ttu-id="4027d-125">[Windows/Linux または][DevtoolsCommandMenu]macOS で選択して、 `Shift` + `Ctrl` + `P` コマンド `Command` + `Shift` + `P` メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="4027d-125">[Open the Command Menu][DevtoolsCommandMenu], by selecting `Shift`+`Ctrl`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
1.  <span data-ttu-id="4027d-126">文字の `>` 後に、 `dock` と入力し、次のいずれかのコマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="4027d-126">After the `>` character, enter `dock`, and then choose one of the following commands:</span></span>  
    
    *  **<span data-ttu-id="4027d-127">下にドッキングする</span><span class="sxs-lookup"><span data-stu-id="4027d-127">Dock to bottom</span></span>**
    *  **<span data-ttu-id="4027d-128">左にドッキングする</span><span class="sxs-lookup"><span data-stu-id="4027d-128">Dock to left</span></span>**
    *  **<span data-ttu-id="4027d-129">右にドッキングする</span><span class="sxs-lookup"><span data-stu-id="4027d-129">Dock to right</span></span>**
    *  **<span data-ttu-id="4027d-130">最後のドック位置を復元する</span><span class="sxs-lookup"><span data-stu-id="4027d-130">Restore last dock position</span></span>**
    *  **<span data-ttu-id="4027d-131">別のウィンドウへのドッキングを解除する</span><span class="sxs-lookup"><span data-stu-id="4027d-131">Undock into separate window</span></span>**
    
    <span data-ttu-id="4027d-132">メイン メニューからコマンドに [アクセスすることもできます](#change-placement-from-the-main-menu)。</span><span class="sxs-lookup"><span data-stu-id="4027d-132">You may also access the commands from the [main menu](#change-placement-from-the-main-menu).</span></span> 
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="[元に戻す] コマンド" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       <span data-ttu-id="4027d-134">[元に戻す] コマンド</span><span class="sxs-lookup"><span data-stu-id="4027d-134">The Undock command</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4027d-135">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="4027d-135">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "[Microsoft Edge DevTools コマンド] メニューメニューを使用してコマンドを実行|Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="4027d-137">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4027d-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4027d-138">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/customize/placement) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="4027d-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/placement) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4027d-140">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4027d-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
