---
description: DevTools のビジョンのMicrosoft Edgeエミュレートします。
title: DevTools の視覚Microsoft Edgeをエミュレートする (色覚不備)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0a0ee09c2f739beb366b4c39d113b31fb719ec6a
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597122"
---
# <a name="emulate-vision-deficiencies"></a><span data-ttu-id="5ddcd-104">視覚欠陥をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="5ddcd-104">Emulate vision deficiencies</span></span>  

<span data-ttu-id="5ddcd-105">色覚障害[\(color][ColorblindawarenessMain] blindness\) またはぼやけた視力を持つユーザーのニーズをよりよく満たすために[、Microsoft Edge DevTools][DevtoolsIndex]を使用すると、ぼやけた視力と特定の色覚の欠陥をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-105">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\) or blurred vision, [Microsoft Edge DevTools][DevtoolsIndex] allow you to simulate blurred vision and specific color vision deficiencies.</span></span>  <span data-ttu-id="5ddcd-106">[ **ビジョンの不備のエミュレート]** ツールは、次のカテゴリをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-106">The **Emulate vision deficiencies** tool simulates the following categories.</span></span>  

| <span data-ttu-id="5ddcd-107">色覚の不足</span><span class="sxs-lookup"><span data-stu-id="5ddcd-107">Color vision deficiency</span></span> | <span data-ttu-id="5ddcd-108">詳細</span><span class="sxs-lookup"><span data-stu-id="5ddcd-108">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="5ddcd-109">ぼやけたビジョン</span><span class="sxs-lookup"><span data-stu-id="5ddcd-109">Blurred vision</span></span> | <span data-ttu-id="5ddcd-110">ユーザーは詳細に焦点を当てるのが困難です。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-110">The user has difficulty focusing on fine details.</span></span> |  
| <span data-ttu-id="5ddcd-111">Protanopia</span><span class="sxs-lookup"><span data-stu-id="5ddcd-111">Protanopia</span></span> | <span data-ttu-id="5ddcd-112">ユーザーは赤い光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-112">The user is unable to perceive any red light.</span></span> |  
| <span data-ttu-id="5ddcd-113">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="5ddcd-113">Deuteranopia</span></span> | <span data-ttu-id="5ddcd-114">ユーザーは緑色の光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-114">The user is unable to perceive any green light.</span></span> |  
| <span data-ttu-id="5ddcd-115">トリタニア</span><span class="sxs-lookup"><span data-stu-id="5ddcd-115">Tritanopia</span></span> | <span data-ttu-id="5ddcd-116">ユーザーは青色光を認識できません。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-116">The user is unable to perceive any blue light.</span></span> |  
| <span data-ttu-id="5ddcd-117">アクロマトプシア</span><span class="sxs-lookup"><span data-stu-id="5ddcd-117">Achromatopsia</span></span> | <span data-ttu-id="5ddcd-118">ユーザーは色を認識できず、すべての色が灰色の色合いに減少します。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-118">The user is unable to perceive any color, which reduces all color to a shade of grey.</span></span> |  


## <a name="navigate-to-the-rendering-tool"></a><span data-ttu-id="5ddcd-119">[レンダリング] ツールに移動する</span><span class="sxs-lookup"><span data-stu-id="5ddcd-119">Navigate to the Rendering tool</span></span>

<span data-ttu-id="5ddcd-120">Web 製品に適用されているビジョン不足をシミュレートするには、[レンダリング ツール] を [開きます][DevtoolsRenderingToolsIndex]。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-120">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][DevtoolsRenderingToolsIndex].</span></span>  

1.  <span data-ttu-id="5ddcd-121">レンダリング ツールを開く場合は、ツールバー `...` のメニュー項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-121">To open the Rendering tool, choose the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="5ddcd-122">その他 **のツールを選択する**</span><span class="sxs-lookup"><span data-stu-id="5ddcd-122">Choose **More tools**</span></span>  
1.  <span data-ttu-id="5ddcd-123">[レンダリング **] を選択する**</span><span class="sxs-lookup"><span data-stu-id="5ddcd-123">Choose **Rendering**</span></span>  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="レンダリング ツールを開く" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="5ddcd-125">レンダリング ツール **を開** く</span><span class="sxs-lookup"><span data-stu-id="5ddcd-125">Opening the **Rendering** tool</span></span>
    :::image-end:::  
    
<span data-ttu-id="5ddcd-126">[ **レンダリング]** メニューがドロワーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-126">The **Rendering** menu appears in the drawer.</span></span>  

1.  <span data-ttu-id="5ddcd-127">メニュー項目まで下 `Emulate vision deficiencies` にスクロールし、ドロップダウン メニューを選択してオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-127">Scroll down to the `Emulate vision deficiencies` menu item and choose the drop-down menu to display the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="レンダリング ツールの [ビジョンの不備のエミュレート] メニュー" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="5ddcd-129">レンダリング**ツールの [ビジョンの不備\*\*\*\*のエミュレート**] メニュー</span><span class="sxs-lookup"><span data-stu-id="5ddcd-129">The **Emulate vision deficiencies** menu on the **Rendering** tool</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="5ddcd-130">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-130">Choose an option.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="[ビジョンの不備のエミュレート] メニュー オプション" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="5ddcd-132">[ **エミュレートビジョンの欠陥] メニュー** オプション</span><span class="sxs-lookup"><span data-stu-id="5ddcd-132">The **Emulate vision deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5ddcd-133">メイン ウィンドウには、現在のページに適用された選択したオプションのシミュレーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-133">The main windows displays the simulation of your chosen option applied to the current page.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="ぼやけたビジョン シミュレーションを使用して表示する" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="5ddcd-135">ぼや **けたビジョン シミュレーションを使用して表示** する</span><span class="sxs-lookup"><span data-stu-id="5ddcd-135">Display using **Blurred vision** simulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Achromatopsia シミュレーションを使用した表示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="5ddcd-137">**Achromatopsia シミュレーションを使用した**表示</span><span class="sxs-lookup"><span data-stu-id="5ddcd-137">Display using **Achromatopsia** simulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    

## <a name="use-the-command-menu"></a><span data-ttu-id="5ddcd-138">コマンド メニューを使用する</span><span class="sxs-lookup"><span data-stu-id="5ddcd-138">Use the Command Menu</span></span>  

<span data-ttu-id="5ddcd-139">コマンド メニューを使用 **して、** さまざまなシミュレーションにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-139">You may also use **Command Menu** to access the different simulations.</span></span>  

1.  <span data-ttu-id="5ddcd-140">`Ctrl` + `Shift` + `P` コマンド メニューを開Windows `Command` + `Shift` + `P` \(Windows/Linux\) または \(macOS\)**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-140">Select `Ctrl`+`Shift`+`P` \(Windows/Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="5ddcd-142">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="5ddcd-142">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5ddcd-143">[種類 `emulate` ] をクリックし、シミュレートする条件を選択して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-143">Type `emulate`, choose what you want to simulate and choose `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="コマンド メニューで使用できるさまざまなシミュレーション オプション" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="5ddcd-145">コマンド メニューで使用できるさまざまなシミュレーション **オプション**</span><span class="sxs-lookup"><span data-stu-id="5ddcd-145">The different simulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="5ddcd-146">エミュレート **ビジョンの欠陥ツールは** 、各欠陥を持つ人物が製品を見る方法の近似をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-146">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="5ddcd-147">一人一人が異なるので、視力の欠陥は人によって重症度が異なります。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-147">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="5ddcd-148">ユーザーのニーズをよりよく満たすために、問題になる可能性がある色の組み合わせを避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-148">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="5ddcd-149">エミュレート **ビジョンの欠陥ツール** は、製品の完全なアクセシビリティ評価ではありません。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-149">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span></span>  <span data-ttu-id="5ddcd-150">代わりに、 **エミュレートビジョンの欠陥** ツールは、問題を回避するための良い最初のステップを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddcd-150">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span></span>  


## <a name="see-also"></a><span data-ttu-id="5ddcd-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ddcd-151">See also</span></span>

* [<span data-ttu-id="5ddcd-152">ページがぼやけたビジョンで使用できると確認する</span><span class="sxs-lookup"><span data-stu-id="5ddcd-152">Verify that the page is usable with blurred vision</span></span>](test-blurred-vision.md)


<!-- links -->  
[DevToolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsRenderingToolsIndex]: ../rendering-tools/index.md "ランタイム パフォーマンス の分析|Microsoft Docs"  

[ColorblindawarenessMain]: https://www.colourblindawareness.org "カラー ブラインドの認識組織"  

[AmfcbMain]: https://www.amfcb.org "カラー ブラインド (AFCB) のアメリカンファンデーション"  
