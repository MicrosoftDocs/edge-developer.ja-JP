---
description: '[レンダリング] ツールの [エミュレートビジョンの欠陥] ドロップダウン リストを使用して、色覚を持つユーザーが Web ページを使用できる点を確認します。'
title: 色覚を持つユーザーがページを使用できると確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 54cd7230f0402bfeb4b5ee28d2bcd0947794676f
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597529"
---
# <a name="verify-that-the-page-is-usable-by-people-with-color-blindness"></a><span data-ttu-id="2eff8-104">色覚を持つユーザーがページを使用できると確認する</span><span class="sxs-lookup"><span data-stu-id="2eff8-104">Verify that the page is usable by people with color blindness</span></span>

<!-- Rendering tool: Emulate vision deficiencies: Protanopia -->

<span data-ttu-id="2eff8-105">色覚を持つユーザーが Web ページを使用できるのを確認\*\*\*\* するには、[レンダリング] ツールで 、[エミュレートビジョンの欠陥] ドロップダウン リスト**を**使用します。</span><span class="sxs-lookup"><span data-stu-id="2eff8-105">To check that a webpage is usable by people with color blindness, in the **Rendering** tool, use the **Emulate vision deficiencies** dropdown list.</span></span>

<span data-ttu-id="2eff8-106">アクセシビリティ テストのデモ Web ページでは、異なる寄付の状態で色が区別の唯一の手段として使用されます。</span><span class="sxs-lookup"><span data-stu-id="2eff8-106">On the accessibility-testing demo webpage, the different donation states use color as the only means of differentiation.</span></span>
*  <span data-ttu-id="2eff8-107">緑は、大量の寄付が受け取られたという意味です。</span><span class="sxs-lookup"><span data-stu-id="2eff8-107">Green means a high amount of donations have been received.</span></span>
*  <span data-ttu-id="2eff8-108">黄色は、中程度の量の寄付が受け取られたという意味です。</span><span class="sxs-lookup"><span data-stu-id="2eff8-108">Yellow means a medium amount of donations have been received.</span></span>
*  <span data-ttu-id="2eff8-109">赤は、少ない量の寄付が受け取られたという意味です。</span><span class="sxs-lookup"><span data-stu-id="2eff8-109">Red means a low amount of donations have been received.</span></span>

<span data-ttu-id="2eff8-110">ただし、すべてのユーザーにこれらの色が意図した通り表示されるとは限らない。</span><span class="sxs-lookup"><span data-stu-id="2eff8-110">But you can't expect all of your users to experience these colors as intended.</span></span>  <span data-ttu-id="2eff8-111">レンダリング ツールの **[ビジョン**の不備\*\*\*\* をエミュレートする] 機能を使用すると、異なるビジョンを持つユーザーがデザインをどのように認識するのかシミュレーションすることで、このデザインが十分ではないと分かっています。</span><span class="sxs-lookup"><span data-stu-id="2eff8-111">By using the **Emulate vision deficiencies** feature of the **Rendering** tool, you can find out that this design is not good enough, by simulating how people with different vision would perceive your design.</span></span>


<span data-ttu-id="2eff8-112">色覚を持つユーザーが Web ページを使用できるかどうかを確認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="2eff8-112">To check whether a webpage is usable by people with color blindness:</span></span>

1.  <span data-ttu-id="2eff8-113">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="2eff8-113">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="2eff8-114">**[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2eff8-114">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="2eff8-115">ドロワー **+** の上部にあるアイコンを選択してツールの一覧を表示し、[レンダリング] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2eff8-115">Select the **+** icon at the top of the Drawer to see the list of tools, and then select **Rendering**.</span></span>  

1.  <span data-ttu-id="2eff8-116">[エミュレート **ビジョンの欠陥] ドロップダウン リスト** で **、[Protanopia] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2eff8-116">In the **Emulate vision deficiencies** dropdown list, select **Protanopia**.</span></span>  <span data-ttu-id="2eff8-117">_Protanopia は_ 赤色光に対する感度が低下し、緑、赤、黄色の区別が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="2eff8-117">_Protanopia_ is reduced sensitivity to red light, making it hard to differentiate green, red, and yellow.</span></span>

    :::image type="complex" source="../media/a11y-testing-simulating-protanopia.msft.png" alt-text="protanopia を持つユーザーとしてドキュメントを表示すると、ドキュメントが表示されます" lightbox="../media/a11y-testing-simulating-protanopia.msft.png":::
        <span data-ttu-id="2eff8-119">protanopia を持つユーザーとしてドキュメントを表示すると、ドキュメントが表示されます</span><span class="sxs-lookup"><span data-stu-id="2eff8-119">Showing the document as someone with protanopia would see it</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="2eff8-120">[レンダリング **] ツールの** [ **ビジョンの不備をエミュレートする]** の下で、[エミュレーションなし] **を選択して** シミュレーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="2eff8-120">In the **Rendering** tool, below **Emulate vision deficiencies**, select **No emulation** to remove the simulation.</span></span>


## <a name="see-also"></a><span data-ttu-id="2eff8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="2eff8-121">See also</span></span>

*  <span data-ttu-id="2eff8-122">[エミュレートビジョンの欠陥][DevToolsVisionDeficiencies]- Protanopia、Deuteranopia、Tritanopia、および Achromatopsia を含む、エミュレートビジョンの欠陥ドロップダウン リスト内のアイテムを定義します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2eff8-122">[Emulate vision deficiencies][DevToolsVisionDeficiencies] - Defines the items in the **Emulate vision deficiencies** dropdown list, including Protanopia, Deuteranopia, Tritanopia, and Achromatopsia.</span></span>
*  [<span data-ttu-id="2eff8-123">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="2eff8-123">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="2eff8-124">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="2eff8-124">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsVisionDeficiencies]: ./emulate-vision-deficiencies.md "ビジョンの欠陥をエミュレート|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
