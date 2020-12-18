---
description: Microsoft Edge DevTools で視覚の不備をエミュレートします。
title: Microsoft Edge DevTools で視覚の不備をエミュレートする (色覚不覚)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5343d32992880f8c60501a86db6cb3a92f417331
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230825"
---
# <span data-ttu-id="b29a1-104">視覚欠陥をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="b29a1-104">Emulate vision deficiencies</span></span>

<span data-ttu-id="b29a1-105">色覚に不備があるユーザーのニーズ[][ColorblindawarenessMain]を満たすために[、Microsoft Edge DevTools][DevtoolsIndex]を使用すると、特定の色覚に対する不備をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="b29a1-105">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\), [Microsoft Edge DevTools][DevtoolsIndex] enable you to simulate specific color vision deficiencies.</span></span>  <span data-ttu-id="b29a1-106">**Emulate vision 不備ツールは**、次のカテゴリをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="b29a1-106">The **Emulate vision deficiencies** tool simulates the following categories.</span></span>  

| <span data-ttu-id="b29a1-107">色覚に対する不備</span><span class="sxs-lookup"><span data-stu-id="b29a1-107">Color vision deficiency</span></span> | <span data-ttu-id="b29a1-108">詳細</span><span class="sxs-lookup"><span data-stu-id="b29a1-108">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="b29a1-109">ぼやけた視覚</span><span class="sxs-lookup"><span data-stu-id="b29a1-109">Blurred vision</span></span> | <span data-ttu-id="b29a1-110">ユーザーは詳細に焦点を当てに困難を持っています。</span><span class="sxs-lookup"><span data-stu-id="b29a1-110">The user has difficulty focusing on fine details.</span></span> |   
| <span data-ttu-id="b29a1-111">プロタニア語</span><span class="sxs-lookup"><span data-stu-id="b29a1-111">Protanopia</span></span> | <span data-ttu-id="b29a1-112">ユーザーは赤い光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="b29a1-112">The user is unable to perceive any red light.</span></span> |  
| <span data-ttu-id="b29a1-113">Deuteranute</span><span class="sxs-lookup"><span data-stu-id="b29a1-113">Deuteranopia</span></span> | <span data-ttu-id="b29a1-114">ユーザーは緑色の光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="b29a1-114">The user is unable to perceive any green light.</span></span> |  
| <span data-ttu-id="b29a1-115">トリタニア</span><span class="sxs-lookup"><span data-stu-id="b29a1-115">Tritanopia</span></span> | <span data-ttu-id="b29a1-116">ユーザーは青色の光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="b29a1-116">The user is unable to perceive any blue light.</span></span> |  
| <span data-ttu-id="b29a1-117">Achromatopsia</span><span class="sxs-lookup"><span data-stu-id="b29a1-117">Achromatopsia</span></span> | <span data-ttu-id="b29a1-118">ユーザーは色を認識できず、すべての色を灰色の網掛けに減らします。</span><span class="sxs-lookup"><span data-stu-id="b29a1-118">The user is unable to perceive any color, which reduces all color to a shade of grey.</span></span> |  

## <span data-ttu-id="b29a1-119">レンダリング ツールに移動する</span><span class="sxs-lookup"><span data-stu-id="b29a1-119">Navigate to the Rendering Tools</span></span>  

<span data-ttu-id="b29a1-120">Web 製品に適用されている視覚障害をシミュレートするには、レンダリング ツールを [開きます][DevtoolsRenderingToolsIndex]。</span><span class="sxs-lookup"><span data-stu-id="b29a1-120">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][DevtoolsRenderingToolsIndex].</span></span>  

1.  <span data-ttu-id="b29a1-121">レンダリング ツールを開くには、ツール バーの `...` メニュー項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29a1-121">To open the Rendering Tools, by choose the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="b29a1-122">選択</span><span class="sxs-lookup"><span data-stu-id="b29a1-122">Choose</span></span> `More tools`  
1.  <span data-ttu-id="b29a1-123">選択</span><span class="sxs-lookup"><span data-stu-id="b29a1-123">Choose</span></span> `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリング ツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="b29a1-125">レンダリング ツール **を開く**</span><span class="sxs-lookup"><span data-stu-id="b29a1-125">Opening the **Rendering Tools**</span></span>  
    :::image-end:::  

<span data-ttu-id="b29a1-126">レンダリング **メニュー** がドロワーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b29a1-126">The **Rendering** menu appears in the drawer.</span></span>  

1.  <span data-ttu-id="b29a1-127">メニュー項目まで下にスクロールし、ドロップダウン メニューを `Emulate vision deficiencies` 選択してオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="b29a1-127">Scroll down to the `Emulate vision deficiencies` menu item and choose the drop-down menu to display the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダリング ドロワーの [Emulate Vision の不備] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="b29a1-129">レンダリング**ドロワーの [Emulate vision の**不備]**メニュー**</span><span class="sxs-lookup"><span data-stu-id="b29a1-129">The **Emulate vision deficiencies** menu on the **Rendering** drawer</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b29a1-130">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b29a1-130">Choose an option.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[Emulate Vision の不備] メニュー オプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="b29a1-132">[ **エミュレートする視覚の不備] メニュー** オプション</span><span class="sxs-lookup"><span data-stu-id="b29a1-132">The **Emulate vision deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b29a1-133">メイン ウィンドウには、現在のページに適用されている選択したオプションのシミュレーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b29a1-133">The main windows displays the simulation of your chosen option applied to the current page.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="[ぼやけた視覚\*\* シミュレーションを使用して表示する]" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="b29a1-135">ぼや **けた視覚シミュレーションを使用して表示** する</span><span class="sxs-lookup"><span data-stu-id="b29a1-135">Display using **Blurred Vision** simulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Display using **Achromatopsia** simulation" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="b29a1-137">**Achromatopsia シミュレーションを使用して表示**する</span><span class="sxs-lookup"><span data-stu-id="b29a1-137">Display using **Achromatopsia** simulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <span data-ttu-id="b29a1-138">コマンド メニューを使用する</span><span class="sxs-lookup"><span data-stu-id="b29a1-138">Use the Command Menu</span></span>  

<span data-ttu-id="b29a1-139">コマンド メニューを使用 **して、さまざまな** シミュレーションにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b29a1-139">You may also use **Command Menu** to access the different simulations.</span></span>  

1.  <span data-ttu-id="b29a1-140">`Control` + `Shift` + `P` \(Windows\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニュー**を開きます**。</span><span class="sxs-lookup"><span data-stu-id="b29a1-140">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="b29a1-142">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="b29a1-142">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b29a1-143">Type `emulate` , choose what you want to simulate and select `Enter` .</span><span class="sxs-lookup"><span data-stu-id="b29a1-143">Type `emulate`, choose what you want to simulate and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンド メニューで使用できるさまざまなシミュレーション オプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="b29a1-145">コマンド メニューで使用できるさまざまなシミュレーション **オプション**</span><span class="sxs-lookup"><span data-stu-id="b29a1-145">The different simulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="b29a1-146">**Emulate vision の不備ツールは**、各不備を持つ人が製品を見る方法の近似値をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="b29a1-146">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="b29a1-147">人は人それぞれ異なっているので、視覚に対する不備は人によって重大度が異なります。</span><span class="sxs-lookup"><span data-stu-id="b29a1-147">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="b29a1-148">ユーザーのニーズをより良く満たすために、問題になる可能性がある色の組み合わせは避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b29a1-148">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="b29a1-149">**Emulate vision 不備ツール**は、製品の完全なアクセシビリティ評価ではありません。</span><span class="sxs-lookup"><span data-stu-id="b29a1-149">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span></span>  <span data-ttu-id="b29a1-150">代わりに **、Emulate vision 不備** ツールを使用すると、問題を回避するための良い第一歩を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b29a1-150">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span></span>  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsRenderingToolsIndex]: ../rendering-tools/index.md "実行時のパフォーマンスを分析する |Microsoft Docs"  

[ColorblindawarenessMain]: http://www.colourblindawareness.org "視覚に対する意識向上組織"  

[AmfcbMain]: https://www.amfcb.org "カラー ブラインドのための American Foundation (AFCB)"  

