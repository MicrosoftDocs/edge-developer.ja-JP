---
description: '[アクセシビリティ] タブを使用してアクセシビリティをテストします。'
title: '[アクセシビリティ] タブを使用してアクセシビリティをテストする'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 839feed56fc82af2b4d96a081c476696166075b9
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597564"
---
<!-- this article was created on 05/11/2021 by moving a section out from the "Accessibility reference" article (reference.md) -->
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
# <a name="test-accessibility-using-the-accessibility-tab"></a><span data-ttu-id="1dec0-104">[アクセシビリティ] タブを使用してアクセシビリティをテストする</span><span class="sxs-lookup"><span data-stu-id="1dec0-104">Test accessibility using the Accessibility tab</span></span>

<span data-ttu-id="1dec0-105">[ **アクセシビリティ] タブ** では、DOM ノードのアクセシビリティ ツリー、ARIA 属性、および計算されたアクセシビリティ プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1dec0-105">The **Accessibility** tab is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span></span>  

<span data-ttu-id="1dec0-106">[アクセシビリティ] **タブを開く** 方法:</span><span class="sxs-lookup"><span data-stu-id="1dec0-106">To open the **Accessibility** tab:</span></span>

1.  <span data-ttu-id="1dec0-107">[要素] **ツールを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="1dec0-107">Select the **Elements** tool.</span></span>  
1.  <span data-ttu-id="1dec0-108">DOM ツリー **で、** 検査する要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="1dec0-108">In the **DOM Tree**, select the element which you want to inspect.</span></span>  
1.  <span data-ttu-id="1dec0-109">[アクセシビリティ **] タブを選択** します。 [スタイル] タブの右側 **にある** [その他のタブ] \( [その他のタブ] ボタン \) ボタンを最初 ![ に選択 ](../media/more-tabs-icon.msft.png) する **必要がある場合** があります。</span><span class="sxs-lookup"><span data-stu-id="1dec0-109">Select the **Accessibility** tab.  You might need to first select the **More tabs** \(![the More tabs button](../media/more-tabs-icon.msft.png)\) button to the right of the **Styles** tab.</span></span>

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="[アクセシビリティ] タブで DevTools ホームページの h1 要素を調す" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   <span data-ttu-id="1dec0-111">[アクセシビリティ `h1` ] タブで DevTools ホームページの **要素を調** す</span><span class="sxs-lookup"><span data-stu-id="1dec0-111">Inspect the `h1` element of the DevTools homepage in the **Accessibility** tab</span></span>
:::image-end:::  


## <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a><span data-ttu-id="1dec0-112">アクセシビリティ ツリーで要素の位置を表示する</span><span class="sxs-lookup"><span data-stu-id="1dec0-112">View the position of an element in the Accessibility Tree</span></span>

<span data-ttu-id="1dec0-113">アクセシビリティ [ツリーは、DOM][MDNAccessibilityTree] ツリーのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="1dec0-113">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span></span>  <span data-ttu-id="1dec0-114">アクセシビリティ ツリーには、スクリーン リーダーなどの支援テクノロジを使用してページのコンテンツを表示する場合に役立つ DOM ツリーの要素だけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1dec0-114">The accessibility tree only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page through assistive technologies such as screen readers.</span></span>

<span data-ttu-id="1dec0-115">アクセシビリティ ツリー内の要素の位置を [アクセシビリティ] タブ **から調** えます。</span><span class="sxs-lookup"><span data-stu-id="1dec0-115">Inspect the position of an element in the accessibility tree from the **Accessibility** tab.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="[アクセシビリティ ツリー] セクション" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   <span data-ttu-id="1dec0-117">[ **アクセシビリティ ツリー]** セクション</span><span class="sxs-lookup"><span data-stu-id="1dec0-117">The **Accessibility Tree** section</span></span>  
:::image-end:::  


## <a name="view-the-aria-attributes-of-an-element"></a><span data-ttu-id="1dec0-118">要素の ARIA 属性を表示する</span><span class="sxs-lookup"><span data-stu-id="1dec0-118">View the ARIA attributes of an element</span></span>  

<span data-ttu-id="1dec0-119">ARIA 属性を使用すると、スクリーン リーダーなどの支援テクノロジには、ページの内容を適切に表現するために必要なすべての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1dec0-119">ARIA attributes ensure that assistive technologies such as screen readers have all of the information that they need in order to properly represent the contents of a page.</span></span>  

<span data-ttu-id="1dec0-120">[アクセシビリティ] タブで要素の ARIA 属性 **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="1dec0-120">View the ARIA attributes of an element in the **Accessibility** tab.</span></span>

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="[ARIA 属性] セクション" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   <span data-ttu-id="1dec0-122">**[ARIA 属性]** セクション</span><span class="sxs-lookup"><span data-stu-id="1dec0-122">The **ARIA Attributes** section</span></span>  
:::image-end:::  


## <a name="view-the-computed-accessibility-properties-of-an-element"></a><span data-ttu-id="1dec0-123">要素の計算されたアクセシビリティ プロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="1dec0-123">View the computed accessibility properties of an element</span></span>  


<span data-ttu-id="1dec0-124">一部のアクセシビリティ プロパティは、ブラウザーによって動的に計算されます。</span><span class="sxs-lookup"><span data-stu-id="1dec0-124">Some accessibility properties are dynamically calculated by the browser.</span></span>  <span data-ttu-id="1dec0-125">これらのプロパティは、[アクセシビリティ] タブ **の [計算されたプロパティ** ] **セクションに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1dec0-125">These properties are displayed in the **Computed Properties** section of the **Accessibility** tab.</span></span>  

<span data-ttu-id="1dec0-126">[アクセシビリティ] タブで、要素の計算されたアクセシビリティ プロパティ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="1dec0-126">View the computed accessibility properties of an element in the **Accessibility** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="1dec0-127">計算された CSS プロパティの場合は、[計算] [タブを使用][DevtoolsCssReferenceViewActuallyAppliedElements] します。</span><span class="sxs-lookup"><span data-stu-id="1dec0-127">For computed CSS properties, use the [Computed][DevtoolsCssReferenceViewActuallyAppliedElements] tab.</span></span>

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="[アクセシビリティ] タブの [計算されたプロパティ] セクション" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   <span data-ttu-id="1dec0-129">[ **アクセシビリティ] タブの** [計算された **プロパティ]** セクション</span><span class="sxs-lookup"><span data-stu-id="1dec0-129">The **Computed Properties** section of the **Accessibility** tab</span></span>  
:::image-end:::  


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1dec0-130">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="1dec0-130">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> <span data-ttu-id="1dec0-131">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dec0-131">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1dec0-132">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="1dec0-132">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1dec0-134">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1dec0-134">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- links -->
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "要素に実際に適用される CSS のみを表示する - CSS リファレンス |Microsoft Docs"  
[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "アクセシビリティ ツリー (AOM) |MDN"  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
