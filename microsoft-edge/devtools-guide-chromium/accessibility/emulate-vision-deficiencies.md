---
title: Microsoft Edge DevTools でビジョンの不備をエミュレートする (色覚障碍)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b70499fa189d162fa7589966bab183f4c12f68f7
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843922"
---
# <span data-ttu-id="44f43-103">ビジョンの欠陥のエミュレート</span><span class="sxs-lookup"><span data-stu-id="44f43-103">Emulate vision deficiencies</span></span>

<span data-ttu-id="44f43-104">[カラービジョンの欠陥][ColorblindawarenessMain]を持つユーザーのニーズをより適切に満たすために、 [Microsoft Edge devtools][MicrosoftEdgeDevTools]を使用すると、特定の色ビジョンの不備をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="44f43-104">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\), [Microsoft Edge DevTools][MicrosoftEdgeDevTools] enable you to simulate specific color vision deficiencies.</span></span>  <span data-ttu-id="44f43-105">**ビジョンのエミュレート**ツールでは、次のカテゴリがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="44f43-105">The **Emulate vision deficiencies** tool simulates the following categories.</span></span>  

| <span data-ttu-id="44f43-106">カラービジョンの欠陥</span><span class="sxs-lookup"><span data-stu-id="44f43-106">Color vision deficiency</span></span> | <span data-ttu-id="44f43-107">詳細</span><span class="sxs-lookup"><span data-stu-id="44f43-107">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="44f43-108">ぼやけたビジョン</span><span class="sxs-lookup"><span data-stu-id="44f43-108">Blurred vision</span></span> | <span data-ttu-id="44f43-109">ユーザーは、細かい詳細を重視しています。</span><span class="sxs-lookup"><span data-stu-id="44f43-109">The user has difficulty focusing on fine details.</span></span> |   
| <span data-ttu-id="44f43-110">Protanopia</span><span class="sxs-lookup"><span data-stu-id="44f43-110">Protanopia</span></span> | <span data-ttu-id="44f43-111">ユーザーは赤のライトを認識できません。</span><span class="sxs-lookup"><span data-stu-id="44f43-111">The user is unable to perceive any red light.</span></span> |  
| <span data-ttu-id="44f43-112">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="44f43-112">Deuteranopia</span></span> | <span data-ttu-id="44f43-113">ユーザーは、緑色の光を認識することはできません。</span><span class="sxs-lookup"><span data-stu-id="44f43-113">The user is unable to perceive any green light.</span></span> |  
| <span data-ttu-id="44f43-114">Tritanopia</span><span class="sxs-lookup"><span data-stu-id="44f43-114">Tritanopia</span></span> | <span data-ttu-id="44f43-115">ユーザーは青色の光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="44f43-115">The user is unable to perceive any blue light.</span></span> |  
| <span data-ttu-id="44f43-116">Achroopsia</span><span class="sxs-lookup"><span data-stu-id="44f43-116">Achromatopsia</span></span> | <span data-ttu-id="44f43-117">ユーザーは色を認識することはできません。これにより、すべての色が灰色の階調に縮小されます。</span><span class="sxs-lookup"><span data-stu-id="44f43-117">The user is unable to perceive any color, which reduces all color to a shade of grey.</span></span> |  

## <span data-ttu-id="44f43-118">レンダリングツールに移動する</span><span class="sxs-lookup"><span data-stu-id="44f43-118">Navigate to the Rendering Tools</span></span>  

<span data-ttu-id="44f43-119">Web 製品に対してビジョンの欠陥が適用されていることをシミュレートするには、[レンダリングツール][RenderingTools]を開きます。</span><span class="sxs-lookup"><span data-stu-id="44f43-119">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][RenderingTools].</span></span>  

1.  <span data-ttu-id="44f43-120">`...`ツールバーのメニュー項目を選択して、レンダリングツールを開く</span><span class="sxs-lookup"><span data-stu-id="44f43-120">Open the Rendering Tools by selecting the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="44f43-121">選択する</span><span class="sxs-lookup"><span data-stu-id="44f43-121">Select</span></span> `More tools`  
1.  <span data-ttu-id="44f43-122">選択する</span><span class="sxs-lookup"><span data-stu-id="44f43-122">Select</span></span> `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリングツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="44f43-124">**レンダリングツール**を開く</span><span class="sxs-lookup"><span data-stu-id="44f43-124">Opening the **Rendering Tools**</span></span>  
    :::image-end:::  

<span data-ttu-id="44f43-125">[**レンダリング**] メニューが [ドロアー] に表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f43-125">The **Rendering** menu appears in the drawer.</span></span>  

1.  <span data-ttu-id="44f43-126">メニュー項目まで下にスクロール `Emulate vision deficiencies` し、ドロップダウンメニューを選択してオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="44f43-126">Scroll down to the `Emulate vision deficiencies` menu item and select the drop-down menu to display the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダードロアーの [ビジョンの欠陥のエミュレート] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="44f43-128">**レンダー**ドロアーの [**ビジョンの欠陥のエミュレート**] メニュー</span><span class="sxs-lookup"><span data-stu-id="44f43-128">The **Emulate vision deficiencies** menu on the **Rendering** drawer</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="44f43-129">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="44f43-129">Choose an option.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[視覚障碍のエミュレート] メニューのオプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="44f43-131">[**視覚障碍のエミュレート**] メニューのオプション</span><span class="sxs-lookup"><span data-stu-id="44f43-131">The **Emulate vision deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="44f43-132">メインウィンドウには、現在のページに適用されているオプションのシミュレーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f43-132">The main windows displays the simulation of your selected option applied to the current page.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="ディスプレイの使用 \* \* ぼやけたビジョン \* \* シミュレーション" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="44f43-134">ぼやけた**ビジョン**シミュレーションを使って表示する</span><span class="sxs-lookup"><span data-stu-id="44f43-134">Display using **Blurred Vision** simulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="\* \* Achromatopsia \* \* シミュレーションを使用して表示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="44f43-136">**Achromatopsia**シミュレーションを使った表示</span><span class="sxs-lookup"><span data-stu-id="44f43-136">Display using **Achromatopsia** simulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <span data-ttu-id="44f43-137">コマンドメニューを使用する</span><span class="sxs-lookup"><span data-stu-id="44f43-137">Use the Command Menu</span></span>  

<span data-ttu-id="44f43-138">**コマンドメニュー**を使用して、さまざまなシミュレーションにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="44f43-138">You may also use **Command Menu** to access the different simulations.</span></span>  

1.  <span data-ttu-id="44f43-139">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="44f43-139">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="44f43-141">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="44f43-141">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="44f43-142">「」と入力し `emulate` 、シミュレートするものを選択して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="44f43-142">Type `emulate`, choose what you want to simulate and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンドメニューで使用できるさまざまなシミュレーションオプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="44f43-144">**コマンドメニュー**で使用できるさまざまなシミュレーションオプション</span><span class="sxs-lookup"><span data-stu-id="44f43-144">The different simulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="44f43-145">**ビジョンのエミュレート**ツールでは、各欠陥のあるユーザーが製品をどのように表示するかの概算をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="44f43-145">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="44f43-146">各ユーザーは異なるため、視覚障碍はユーザーによって深刻されます。</span><span class="sxs-lookup"><span data-stu-id="44f43-146">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="44f43-147">ユーザーのニーズをより適切に満たすために、問題が発生する可能性のある色の組み合わせは避けてください。</span><span class="sxs-lookup"><span data-stu-id="44f43-147">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="44f43-148">**ビジョンのエミュレート**ツールは、製品の完全なアクセシビリティ評価ではありません。</span><span class="sxs-lookup"><span data-stu-id="44f43-148">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span></span>  <span data-ttu-id="44f43-149">代わりに、**ビジョンの欠陥**ツールをエミュレートすることで、問題を回避するための最初の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f43-149">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span></span>  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org "色覚障碍のある組織"  
[AmfcbMain]: https://www.amfcb.org "色ブラインド (AFCB) のアメリカの基盤"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge (Chromium) のレンダリングツール"  
