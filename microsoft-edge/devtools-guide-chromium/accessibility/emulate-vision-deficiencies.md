---
description: DevTools のビジョンのMicrosoft Edgeエミュレートします。
title: DevTools の視覚Microsoft Edgeをエミュレートする (色覚不備)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1ab224f1dc70618dbef77ec6e6dbc22a0d1f47fb
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564603"
---
# <a name="emulate-vision-deficiencies"></a><span data-ttu-id="3016e-104">視覚欠陥をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="3016e-104">Emulate vision deficiencies</span></span>  

<span data-ttu-id="3016e-105">色覚障害[\(color][ColorblindawarenessMain] blindness\) を持つユーザーのニーズをよりよく満たすために[、Microsoft Edge DevTools][DevtoolsIndex]を使用すると、特定の色覚障害をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="3016e-105">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\), [Microsoft Edge DevTools][DevtoolsIndex] allow you to simulate specific color vision deficiencies.</span></span>  <span data-ttu-id="3016e-106">[ **ビジョンの不備のエミュレート]** ツールは、次のカテゴリをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="3016e-106">The **Emulate vision deficiencies** tool simulates the following categories.</span></span>  

| <span data-ttu-id="3016e-107">色覚の不足</span><span class="sxs-lookup"><span data-stu-id="3016e-107">Color vision deficiency</span></span> | <span data-ttu-id="3016e-108">詳細</span><span class="sxs-lookup"><span data-stu-id="3016e-108">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="3016e-109">ぼやけたビジョン</span><span class="sxs-lookup"><span data-stu-id="3016e-109">Blurred vision</span></span> | <span data-ttu-id="3016e-110">ユーザーは詳細に焦点を当てるのが困難です。</span><span class="sxs-lookup"><span data-stu-id="3016e-110">The user has difficulty focusing on fine details.</span></span> |  
| <span data-ttu-id="3016e-111">Protanopia</span><span class="sxs-lookup"><span data-stu-id="3016e-111">Protanopia</span></span> | <span data-ttu-id="3016e-112">ユーザーは赤い光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="3016e-112">The user is unable to perceive any red light.</span></span> |  
| <span data-ttu-id="3016e-113">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="3016e-113">Deuteranopia</span></span> | <span data-ttu-id="3016e-114">ユーザーは緑色の光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="3016e-114">The user is unable to perceive any green light.</span></span> |  
| <span data-ttu-id="3016e-115">トリタニア</span><span class="sxs-lookup"><span data-stu-id="3016e-115">Tritanopia</span></span> | <span data-ttu-id="3016e-116">ユーザーは青色光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="3016e-116">The user is unable to perceive any blue light.</span></span> |  
| <span data-ttu-id="3016e-117">アクロマトプシア</span><span class="sxs-lookup"><span data-stu-id="3016e-117">Achromatopsia</span></span> | <span data-ttu-id="3016e-118">ユーザーは色を認識できず、すべての色が灰色の色合いに減少します。</span><span class="sxs-lookup"><span data-stu-id="3016e-118">The user is unable to perceive any color, which reduces all color to a shade of grey.</span></span> |  

## <a name="navigate-to-the-rendering-tools"></a><span data-ttu-id="3016e-119">[レンダリング ツール] に移動する</span><span class="sxs-lookup"><span data-stu-id="3016e-119">Navigate to the Rendering Tools</span></span>  

<span data-ttu-id="3016e-120">Web 製品に適用されているビジョン不足をシミュレートするには、[レンダリング ツール] を [開きます][DevtoolsRenderingToolsIndex]。</span><span class="sxs-lookup"><span data-stu-id="3016e-120">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][DevtoolsRenderingToolsIndex].</span></span>  

1.  <span data-ttu-id="3016e-121">レンダリング ツールを開く場合は、ツールバー `...` のメニュー項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="3016e-121">To open the Rendering Tools, choose the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="3016e-122">その他 **のツールを選択する**</span><span class="sxs-lookup"><span data-stu-id="3016e-122">Choose **More tools**</span></span>  
1.  <span data-ttu-id="3016e-123">[レンダリング **] を選択する**</span><span class="sxs-lookup"><span data-stu-id="3016e-123">Choose **Rendering**</span></span>  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリング ツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="3016e-125">レンダリング ツール **を開く**</span><span class="sxs-lookup"><span data-stu-id="3016e-125">Opening the **Rendering Tools**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="3016e-126">[ **レンダリング]** メニューがドロワーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3016e-126">The **Rendering** menu appears in the drawer.</span></span>  

1.  <span data-ttu-id="3016e-127">メニュー項目まで下 `Emulate vision deficiencies` にスクロールし、ドロップダウン メニューを選択してオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="3016e-127">Scroll down to the `Emulate vision deficiencies` menu item and choose the drop-down menu to display the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダリング ドロワーの [ビジョンの不備のエミュレート] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="3016e-129">レンダリング**ドロワーの [ビジョンの不備**のエミュレート]**メニュー**</span><span class="sxs-lookup"><span data-stu-id="3016e-129">The **Emulate vision deficiencies** menu on the **Rendering** drawer</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3016e-130">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3016e-130">Choose an option.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[ビジョンの不備のエミュレート] メニュー オプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="3016e-132">[ **エミュレートビジョンの欠陥] メニュー** オプション</span><span class="sxs-lookup"><span data-stu-id="3016e-132">The **Emulate vision deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3016e-133">メイン ウィンドウには、現在のページに適用された選択したオプションのシミュレーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3016e-133">The main windows displays the simulation of your chosen option applied to the current page.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="**ぼやけたビジョン** シミュレーションを使用して表示する" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="3016e-135">ぼや **けたビジョン シミュレーションを使用して表示** する</span><span class="sxs-lookup"><span data-stu-id="3016e-135">Display using **Blurred Vision** simulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="**Achromatopsia** シミュレーションを使用した表示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="3016e-137">**Achromatopsia シミュレーションを使用した**表示</span><span class="sxs-lookup"><span data-stu-id="3016e-137">Display using **Achromatopsia** simulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <a name="use-the-command-menu"></a><span data-ttu-id="3016e-138">コマンド メニューを使用する</span><span class="sxs-lookup"><span data-stu-id="3016e-138">Use the Command Menu</span></span>  

<span data-ttu-id="3016e-139">コマンド メニューを使用 **して、** さまざまなシミュレーションにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3016e-139">You may also use **Command Menu** to access the different simulations.</span></span>  

1.  <span data-ttu-id="3016e-140">`Ctrl` + `Shift` + `P` コマンド メニューを開Windows `Command` + `Shift` + `P` \(Windows/Linux\) または \(macOS\)**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3016e-140">Select `Ctrl`+`Shift`+`P` \(Windows/Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="3016e-142">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="3016e-142">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3016e-143">[種類 `emulate` ] をクリックし、シミュレートする条件を選択して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="3016e-143">Type `emulate`, choose what you want to simulate and choose `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンド メニューで使用できるさまざまなシミュレーション オプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="3016e-145">コマンド メニューで使用できるさまざまなシミュレーション **オプション**</span><span class="sxs-lookup"><span data-stu-id="3016e-145">The different simulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="3016e-146">エミュレート **ビジョンの欠陥ツールは** 、各欠陥を持つ人物が製品を見る方法の近似をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="3016e-146">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="3016e-147">一人一人が異なるので、視力の欠陥は人によって重症度が異なります。</span><span class="sxs-lookup"><span data-stu-id="3016e-147">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="3016e-148">ユーザーのニーズをよりよく満たすために、問題になる可能性がある色の組み合わせを避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3016e-148">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="3016e-149">エミュレート **ビジョンの欠陥ツール** は、製品の完全なアクセシビリティ評価ではありません。</span><span class="sxs-lookup"><span data-stu-id="3016e-149">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span></span>  <span data-ttu-id="3016e-150">代わりに、 **エミュレートビジョンの欠陥** ツールは、問題を回避するための良い最初のステップを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3016e-150">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span></span>  

<!-- links -->  

[DevToolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsRenderingToolsIndex]: ../rendering-tools/index.md "ランタイム パフォーマンス の分析|Microsoft Docs"  

[ColorblindawarenessMain]: https://www.colourblindawareness.org "カラー ブラインドの認識組織"  

[AmfcbMain]: https://www.amfcb.org "カラー ブラインド (AFCB) のアメリカンファンデーション"  
