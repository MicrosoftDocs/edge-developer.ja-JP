---
title: Microsoft Edge DevTools でビジョンの不備をエミュレートする (色覚障碍)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0b608f5fe67724eee81aeb993577ee9b45cbca09
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758122"
---
# <span data-ttu-id="eea06-103">ビジョンの欠陥のエミュレート</span><span class="sxs-lookup"><span data-stu-id="eea06-103">Emulate vision deficiencies</span></span>

<span data-ttu-id="eea06-104">世界中の約8% の男性と0.5% は、"色覚障碍" と呼ばれる、一般的に[色ビジョンの欠陥][ColorblindawarenessMain]になっています。</span><span class="sxs-lookup"><span data-stu-id="eea06-104">Worldwide approximately 8% of men and 0.5% of women have a [color vision deficiency][ColorblindawarenessMain] commonly named "Color Blindness".</span></span>  <span data-ttu-id="eea06-105">[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使うと、さまざまな既知の欠陥をエミュレートし、製品のプレビューを表示して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="eea06-105">[Microsoft Edge DevTools][MicrosoftEdgeDevTools] enables you to emulate various known deficiencies and provide a preview of your product for you to review.</span></span>  

| <span data-ttu-id="eea06-106">色の欠陥</span><span class="sxs-lookup"><span data-stu-id="eea06-106">Color Deficiency</span></span> | <span data-ttu-id="eea06-107">詳細</span><span class="sxs-lookup"><span data-stu-id="eea06-107">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="eea06-108">ぼやけたビジョン</span><span class="sxs-lookup"><span data-stu-id="eea06-108">Blurred vision</span></span> |  |   
| <span data-ttu-id="eea06-109">Protanopia</span><span class="sxs-lookup"><span data-stu-id="eea06-109">Protanopia</span></span> | <span data-ttu-id="eea06-110">赤の光を感じることはできません。</span><span class="sxs-lookup"><span data-stu-id="eea06-110">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="eea06-111">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="eea06-111">Deuteranopia</span></span> | <span data-ttu-id="eea06-112">緑の光を感じることはできません。</span><span class="sxs-lookup"><span data-stu-id="eea06-112">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="eea06-113">Tritanopia</span><span class="sxs-lookup"><span data-stu-id="eea06-113">Tritanopia</span></span> | <span data-ttu-id="eea06-114">青い光を感じることはできません。</span><span class="sxs-lookup"><span data-stu-id="eea06-114">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="eea06-115">Achroopsia</span><span class="sxs-lookup"><span data-stu-id="eea06-115">Achromatopsia</span></span> | <span data-ttu-id="eea06-116">灰色の階調を除き、どの色もまったく感じられません。</span><span class="sxs-lookup"><span data-stu-id="eea06-116">The inability to perceive any color, except for shades of grey.</span></span> |  

## <span data-ttu-id="eea06-117">レンダリングツールに移動する</span><span class="sxs-lookup"><span data-stu-id="eea06-117">Navigate to the Rendering Tools</span></span>  

<span data-ttu-id="eea06-118">現在の web 製品で色の欠陥をテストするには、[レンダリングツール][RenderingTools]を開きます。</span><span class="sxs-lookup"><span data-stu-id="eea06-118">To test your current web product for color deficiencies, open the [Rendering Tools][RenderingTools].</span></span>  

1.  <span data-ttu-id="eea06-119">`...`ツールバーのメニュー項目を選択して、レンダリングツールを開く</span><span class="sxs-lookup"><span data-stu-id="eea06-119">Open the Rendering Tools by selecting the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="eea06-120">選択する</span><span class="sxs-lookup"><span data-stu-id="eea06-120">Select</span></span> `More tools`  
1.  <span data-ttu-id="eea06-121">選択する</span><span class="sxs-lookup"><span data-stu-id="eea06-121">Select</span></span> `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリングツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="eea06-123">**レンダリングツール**を開く</span><span class="sxs-lookup"><span data-stu-id="eea06-123">Opening the **Rendering Tools**</span></span>  
    :::image-end:::  

<span data-ttu-id="eea06-124">**レンダリング**メニューは、devtools の下半分に表示されます。</span><span class="sxs-lookup"><span data-stu-id="eea06-124">The **Rendering** menu appears in the bottom half of the DevTools.</span></span>  

1.  <span data-ttu-id="eea06-125">メニュー項目まで下にスクロール `Emulate Vision deficiencies` して、オプションから選びます。</span><span class="sxs-lookup"><span data-stu-id="eea06-125">Scroll down to the `Emulate Vision deficiencies` menu item and select from the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダリングツールの [ビジョンの欠陥のエミュレート] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="eea06-127">**レンダリング**ツールの [**ビジョンの欠陥のエミュレート**] メニュー</span><span class="sxs-lookup"><span data-stu-id="eea06-127">The **Emulate Vision Deficiencies** menu of the **Rendering** tools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="eea06-128">いずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="eea06-128">Choose any of the options</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[視覚障碍のエミュレート] メニューのオプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="eea06-130">[**視覚障碍のエミュレート**] メニューのオプション</span><span class="sxs-lookup"><span data-stu-id="eea06-130">The **Emulate Vision Deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="eea06-131">現在のページは、選択した欠陥によってユーザーにどのように表示されるかをシミュレートして表示されます。</span><span class="sxs-lookup"><span data-stu-id="eea06-131">The current page is displayed in a simulation of how it may appear to a user with the chosen deficiency.</span></span>  

    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="Microsoft Edge 開発者ツールのドキュメント (ぼやけたビジョンエミュレーション)" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="eea06-133">ぼやけた**ビジョン**エミュレーションを使用して表示される</span><span class="sxs-lookup"><span data-stu-id="eea06-133">Displayed using **Blurred Vision** emulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Achroopsia のビジョンエミュレーションの Microsoft Edge 開発者ツールのドキュメント" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="eea06-135">**Achromatopsia のビジョン**エミュレーションを使用して表示する</span><span class="sxs-lookup"><span data-stu-id="eea06-135">Display using **Achromatopsia Vision** emulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <span data-ttu-id="eea06-136">コマンドメニューを使用する</span><span class="sxs-lookup"><span data-stu-id="eea06-136">Using the command menu</span></span>  

<span data-ttu-id="eea06-137">また、**コマンドメニュー**を使用してさまざまなメニューを表示することなく、さまざまなエミュレーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eea06-137">You may also reach the different emulations without going through the various menus using the **Command Menu**.</span></span>  

1.  <span data-ttu-id="eea06-138">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="eea06-138">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="eea06-140">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="eea06-140">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="eea06-141">「」と入力し `emulate` 、シミュレートするものを選択して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="eea06-141">Type `emulate`, choose what you want to simulate and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンドメニューで使用できるさまざまなエミュレーションオプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="eea06-143">**コマンドメニュー**で使用できるさまざまなエミュレーションオプション</span><span class="sxs-lookup"><span data-stu-id="eea06-143">The different emulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="eea06-144">エミュレーションツールは、各不具合のあるユーザーが製品をどのように表示するかを概算したものです。</span><span class="sxs-lookup"><span data-stu-id="eea06-144">The emulation tools are approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="eea06-145">各ユーザーは異なるため、視覚障碍はユーザーによって深刻されます。</span><span class="sxs-lookup"><span data-stu-id="eea06-145">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="eea06-146">ユーザーのニーズをより適切に満たすために、問題が発生する可能性のある色の組み合わせは避けてください。</span><span class="sxs-lookup"><span data-stu-id="eea06-146">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="eea06-147">エミュレーションツールは製品のアクセシビリティを完全に評価するわけではありませんが、最大の欠点を回避するための第一歩として最適です。</span><span class="sxs-lookup"><span data-stu-id="eea06-147">The emulation tools are not a full assessment of the accessibility of your product, but you should have a good first step towards avoiding the biggest deficiencies.</span></span>  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org "色覚障碍のある組織"  
[AmfcbMain]: https://www.amfcb.org "色ブラインド (AFCB) のアメリカの基盤"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge (Chromium) のレンダリングツール"  
