---
description: DevTools のアクセシビリティ機能のMicrosoft Edge参照。
title: アクセシビリティリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a82dec6ffd7e3fb44143ea103fc9756afcd1a161
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564575"
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
# <a name="accessibility-reference"></a><span data-ttu-id="d69c2-104">アクセシビリティリファレンス</span><span class="sxs-lookup"><span data-stu-id="d69c2-104">Accessibility reference</span></span>  

<span data-ttu-id="d69c2-105">このページは、DevTools のアクセシビリティ機能のMicrosoft Edgeです。</span><span class="sxs-lookup"><span data-stu-id="d69c2-105">This page is a comprehensive reference of accessibility features in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="d69c2-106">これは、次の Web 開発者を対象とします。</span><span class="sxs-lookup"><span data-stu-id="d69c2-106">It is intended for web developers who:</span></span>  

*   <span data-ttu-id="d69c2-107">DevTools を開く方法など、基本的な理解を深める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-107">Have a basic understanding of DevTools, such as how to open it.</span></span>  
*   <span data-ttu-id="d69c2-108">アクセシビリティの原則 [とベスト プラクティスに精通しています][MDNAccessibility]。</span><span class="sxs-lookup"><span data-stu-id="d69c2-108">Are familiar with [accessibility principles and best practices][MDNAccessibility].</span></span>  
    
<span data-ttu-id="d69c2-109">この参照の目的は、ページのアクセシビリティを調べるのに役立つ DevTools で利用可能なすべてのツールを見つけるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-109">The purpose of this reference is to help you discover all of the tools available in DevTools that help you examine the accessibility of a page.</span></span>  

<span data-ttu-id="d69c2-110">スクリーン リーダーのような支援テクノロジを使用して DevTools をナビゲートする際のヘルプを探している場合は、「Navigateing Microsoft Edge [DevTools][DevtoolsAccessibilityNavigation]with Assistive Technology 」に移動します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-110">If you are looking for help on navigating DevTools with an assistive technology like a screen reader, navigate to [Navigating Microsoft Edge DevTools With Assistive Technology][DevtoolsAccessibilityNavigation].</span></span>  

## <a name="overview-of-accessibility-features-in-microsoft-edge-devtools"></a><span data-ttu-id="d69c2-111">DevTools のアクセシビリティ機能Microsoft Edge概要</span><span class="sxs-lookup"><span data-stu-id="d69c2-111">Overview of accessibility features in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="d69c2-112">このセクションでは、DevTools がアクセシビリティ ツールキット全体に適合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-112">This section explains how DevTools fits into your overall accessibility toolkit.</span></span>  

<span data-ttu-id="d69c2-113">ページにアクセスできるかどうかを判断するには、次の 2 つの一般的な質問を念頭に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-113">When determining whether a page is accessible, you need to have 2 general questions in mind:</span></span>  

1.  <span data-ttu-id="d69c2-114">キーボードまたはスクリーン リーダーでページを [移動できますか][MDNScreenReader]。</span><span class="sxs-lookup"><span data-stu-id="d69c2-114">Are you able to navigate the page with a keyboard or [screen reader][MDNScreenReader]?</span></span>  
1.  <span data-ttu-id="d69c2-115">ページの要素がスクリーン リーダー用に適切にマークされていますか?</span><span class="sxs-lookup"><span data-stu-id="d69c2-115">Are the elements of the page properly marked up for screen readers?</span></span>  
    
<span data-ttu-id="d69c2-116">一般に、DevTools は、これらのエラーを自動的に検出しやすいため、質問#2に関連するエラーを修正するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-116">In general, DevTools should help you fix errors related to question #2, because these errors are easy to detect in an automated fashion.</span></span>  <span data-ttu-id="d69c2-117">質問#1同様に重要ですが、残念ながら DevTools はそこで役立つとは限らない。</span><span class="sxs-lookup"><span data-stu-id="d69c2-117">Question #1 is just as important, but unfortunately DevTools does not help you there.</span></span>  <span data-ttu-id="d69c2-118">質問に関連するエラーを見つける#1、キーボードまたはスクリーン リーダーを使用してページを使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="d69c2-118">The only way to find errors related to question #1 is to try using a page with a keyboard or screen reader yourself.</span></span>  <!--To learn more, navigate to [How To Do An Accessibility Review][AccessibilityReview].  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <a name="audit-the-accessibility-of-a-page"></a><span data-ttu-id="d69c2-119">ページのアクセシビリティを監査する</span><span class="sxs-lookup"><span data-stu-id="d69c2-119">Audit the accessibility of a page</span></span>  

> [!NOTE]
> <span data-ttu-id="d69c2-120">監査 **ツールは、** サードパーティの Web サイトでホストされているコンテンツへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-120">The **Audits** tool provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="d69c2-121">Microsoft は、これらのサイトのコンテンツおよび収集される可能性があるデータについて責任を負いません。</span><span class="sxs-lookup"><span data-stu-id="d69c2-121">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span></span>  

<span data-ttu-id="d69c2-122">一般に、[監査] パネルを使用して、次の条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-122">In general, use the Audits panel to determine if:</span></span>  

*   <span data-ttu-id="d69c2-123">ページがスクリーン リーダー用に適切にマークされています。</span><span class="sxs-lookup"><span data-stu-id="d69c2-123">A page is properly marked up for screen readers.</span></span>  
*   <span data-ttu-id="d69c2-124">ページ上のテキスト要素には十分なコントラスト比があります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-124">The text elements on a page have sufficient contrast ratios.</span></span>  <span data-ttu-id="d69c2-125">[カラー [ピッカー] でテキスト要素のコントラスト比を表示するに移動します](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)。</span><span class="sxs-lookup"><span data-stu-id="d69c2-125">Navigate to [View the contrast ratio of a text element in the Color Picker](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker).</span></span>  

<span data-ttu-id="d69c2-126">ページを監査するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-126">To audit a page:</span></span>  

1.  <span data-ttu-id="d69c2-127">監査する URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-127">Navigate to the URL that you want to audit.</span></span>  
1.  <span data-ttu-id="d69c2-128">DevTools で、[監査] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-128">In DevTools, choose the **Audits** tool.</span></span>  <span data-ttu-id="d69c2-129">DevTools には、さまざまな構成オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-129">DevTools shows you various configuration options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="監査の構成" lightbox="../media/accessibility-audits-pane.msft.png":::
       <span data-ttu-id="d69c2-131">監査の構成</span><span class="sxs-lookup"><span data-stu-id="d69c2-131">Configure audits</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="d69c2-132">このセクションのスクリーンショットは、バージョン 79 でMicrosoft Edgeされました。</span><span class="sxs-lookup"><span data-stu-id="d69c2-132">The screenshots in this section were taken with Microsoft Edge version 79.</span></span>  <span data-ttu-id="d69c2-133">実行しているバージョンを確認できます `edge://version` 。</span><span class="sxs-lookup"><span data-stu-id="d69c2-133">You may check what version you are running at `edge://version`.</span></span>  <span data-ttu-id="d69c2-134">監査**ツール**の UI は、以前のバージョンのワークフローではMicrosoft Edge異なって見えますが、一般的なワークフローは同じです。</span><span class="sxs-lookup"><span data-stu-id="d69c2-134">The **Audits** tool UI looks different in earlier versions of Microsoft Edge, but the general workflow is the same.</span></span>  
    
1.  <span data-ttu-id="d69c2-135">[ **デバイス]** で、 **モバイル** デバイスをシミュレートする場合は[モバイル] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-135">For **Device**, choose **Mobile** if you want to simulate a mobile device.</span></span>  <span data-ttu-id="d69c2-136">このオプションは、ユーザー エージェントの文字列を変更し、ビューポートのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-136">This option changes your user agent string and resizes the viewport.</span></span>  <span data-ttu-id="d69c2-137">モバイル バージョンのページがデスクトップ バージョンとは異なる場合、このオプションは監査の結果に大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-137">If the mobile version of the page displays differently than the desktop version, this option may have a significant effect on the results of your audit.</span></span>  
1.  <span data-ttu-id="d69c2-138">[監査 **] セクション** で、アクセシビリティが **有効になっているか** 確認します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-138">In the **Audits** section, make sure that **Accessibility** is enabled.</span></span>  <span data-ttu-id="d69c2-139">レポートから除外する場合は、他のカテゴリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d69c2-139">Disable the other categories if you want to exclude them from your report.</span></span>  <span data-ttu-id="d69c2-140">ページの品質を向上させる他の方法を見つけしたい場合は、有効のままにします。</span><span class="sxs-lookup"><span data-stu-id="d69c2-140">Leave them enabled if you want to discover other ways to improve the quality of your page.</span></span>  
1.  <span data-ttu-id="d69c2-141">[ **調整] セクション** では、負荷のパフォーマンスを分析するときに役立つネットワークと CPU を調整できます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-141">The **Throttling** section lets you throttle the network and CPU, which is useful when analyzing load performance.</span></span>  <span data-ttu-id="d69c2-142">このオプションはアクセシビリティ スコアとは無関係である必要があります。そのため、必要に応じて使用できます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-142">This option should be irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="d69c2-143">[**ページのStorage]** チェック ボックスをオンにすると、ページを読み込む前にすべての記憶域をクリアしたり、ページ読み込みの間にストレージを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-143">The **Clear Storage** checkbox lets you clear all storage before loading the page, or preserve storage between page loads.</span></span>  <span data-ttu-id="d69c2-144">このオプションは、アクセシビリティ スコアとは無関係な場合も考え、必要に応じて使用できます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-144">This option is also probably irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="d69c2-145">[ **監査の実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d69c2-145">Choose **Run Audits**.</span></span> <span data-ttu-id="d69c2-146">10 ~ 30 秒後、DevTools はレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-146">After 10 to 30 seconds, DevTools provides a report.</span></span>  <span data-ttu-id="d69c2-147">レポートには、ページのアクセシビリティを向上させる方法に関するさまざまなヒントが示されています。</span><span class="sxs-lookup"><span data-stu-id="d69c2-147">Your report gives you various tips on how to improve the accessibility of the page.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="レポート" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       <span data-ttu-id="d69c2-149">レポート</span><span class="sxs-lookup"><span data-stu-id="d69c2-149">A report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d69c2-150">監査を選択して、詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-150">Choose an audit to learn more about it.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="監査の詳細" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       <span data-ttu-id="d69c2-152">監査の詳細</span><span class="sxs-lookup"><span data-stu-id="d69c2-152">More information about an audit</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d69c2-153">[ **詳細] を選択** して、その監査のドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-153">Choose **Learn More** to view the documentation of that audit.</span></span>  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="監査のドキュメントを表示する" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       <span data-ttu-id="d69c2-155">監査のドキュメントを表示する</span><span class="sxs-lookup"><span data-stu-id="d69c2-155">View the documentation of an audit</span></span>  
    :::image-end:::  
    
### <a name="see-also-axe-extension"></a><span data-ttu-id="d69c2-156">「aXe extension」も参照</span><span class="sxs-lookup"><span data-stu-id="d69c2-156">See also: aXe extension</span></span>  

<span data-ttu-id="d69c2-157">監査ツールではなく [、aXe][ChromeWebStoreAxe] 拡張機能を **使用する方が良** い場合があります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-157">You may prefer to use the [aXe extension][ChromeWebStoreAxe] rather than the **Audits** tool.</span></span>  
<span data-ttu-id="d69c2-158">aXe 拡張機能は、通常、Audits パネルに電力を供給する基になるエンジンであるので、同じ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-158">The aXe extension generally provides the same information, since it is the underlying engine that powers the Audits panel.</span></span>  <span data-ttu-id="d69c2-159">aXe 拡張機能の UI は異なります。監査の説明は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-159">The aXe extension has a different UI and describes audits slightly differently.</span></span>  
<span data-ttu-id="d69c2-160">aXe 拡張機能が **Audits** ツールを超える利点の 1 つは、障害が発生したノードを検査して強調表示できる点です。</span><span class="sxs-lookup"><span data-stu-id="d69c2-160">One advantage that the aXe extension has over the **Audits** tool is that it enables you to inspect and highlight failing nodes.</span></span>  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="aXe 拡張機能" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   <span data-ttu-id="d69c2-162">aXe 拡張機能</span><span class="sxs-lookup"><span data-stu-id="d69c2-162">The aXe extension</span></span>  
:::image-end:::  

## <a name="the-accessibility-panel"></a><span data-ttu-id="d69c2-163">[アクセシビリティ] パネル</span><span class="sxs-lookup"><span data-stu-id="d69c2-163">The Accessibility panel</span></span>  

<span data-ttu-id="d69c2-164">アクセシビリティ **パネルは** 、DOM ノードのアクセシビリティ ツリー、ARIA 属性、および計算されたアクセシビリティ プロパティを表示する場所です。</span><span class="sxs-lookup"><span data-stu-id="d69c2-164">The **Accessibility** panel is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span></span>  

<span data-ttu-id="d69c2-165">[アクセシビリティ] **パネルを開く** 方法は次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d69c2-165">To open the **Accessibility** panel:</span></span>  

1.  <span data-ttu-id="d69c2-166">[要素] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-166">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="d69c2-167">DOM ツリー **で、** 検査する要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-167">In the **DOM Tree**, select the element which you want to inspect.</span></span>  
1.  <span data-ttu-id="d69c2-168">[アクセシビリティ **] パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-168">Choose the **Accessibility** panel.</span></span>  <span data-ttu-id="d69c2-169">このパネルは、[その他のタブ] \( **More Tabs** \) ボタン ![ の ](../media/more-tabs-icon.msft.png) 背後に非表示になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-169">This panel may be hidden behind the **More Tabs** \(![More Tabs](../media/more-tabs-icon.msft.png)\) button.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="アクセシビリティ パネルで DevTools ホームページの h1 要素を検査する" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   <span data-ttu-id="d69c2-171">アクセシビリティ パネル `h1` で DevTools ホームページの **要素を検査** する</span><span class="sxs-lookup"><span data-stu-id="d69c2-171">Inspect the `h1` element of the DevTools homepage in the **Accessibility** panel</span></span>  
:::image-end:::  

### <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a><span data-ttu-id="d69c2-172">アクセシビリティ ツリー内の要素の位置を表示する</span><span class="sxs-lookup"><span data-stu-id="d69c2-172">View the position of an element in the accessibility tree</span></span>  

<span data-ttu-id="d69c2-173">アクセシビリティ [ツリーは、DOM][MDNAccessibilityTree] ツリーのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="d69c2-173">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span></span>  <span data-ttu-id="d69c2-174">これは、スクリーン リーダーにページの内容を表示するために関連し、有用な DOM ツリーの要素のみを含む。</span><span class="sxs-lookup"><span data-stu-id="d69c2-174">It only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span></span>  

<span data-ttu-id="d69c2-175">アクセシビリティ パネルからアクセシビリティ ツリー内の要素の [位置を調](#the-accessibility-panel) えます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-175">Inspect the position of an element in the accessibility tree from the [Accessibility](#the-accessibility-panel) panel.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="[アクセシビリティ ツリー] セクション" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   <span data-ttu-id="d69c2-177">[ **アクセシビリティ ツリー]** セクション</span><span class="sxs-lookup"><span data-stu-id="d69c2-177">The **Accessibility Tree** section</span></span>  
:::image-end:::  

### <a name="view-the-aria-attributes-of-an-element"></a><span data-ttu-id="d69c2-178">要素の ARIA 属性を表示する</span><span class="sxs-lookup"><span data-stu-id="d69c2-178">View the ARIA attributes of an element</span></span>  

<span data-ttu-id="d69c2-179">ARIA 属性を使用すると、ページの内容を適切に表現するために必要なすべての情報がスクリーン リーダーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-179">ARIA attributes ensure that screen readers have all of the information that they need in order to properly represent the contents of a page.</span></span>  

<span data-ttu-id="d69c2-180">アクセシビリティ パネルで要素の ARIA 属性 [を表示](#the-accessibility-panel) します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-180">View the ARIA attributes of an element in the [Accessibility](#the-accessibility-panel) panel.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="[ARIA 属性] セクション" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   <span data-ttu-id="d69c2-182">**[ARIA 属性]** セクション</span><span class="sxs-lookup"><span data-stu-id="d69c2-182">The **ARIA Attributes** section</span></span>  
:::image-end:::  

### <a name="view-the-computed-accessibility-properties-of-an-element"></a><span data-ttu-id="d69c2-183">要素の計算されたアクセシビリティ プロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="d69c2-183">View the computed accessibility properties of an element</span></span>  

> [!NOTE]
> <span data-ttu-id="d69c2-184">計算された CSS プロパティを探している場合は、[計算] [パネルに移動][DevtoolsCssReferenceViewActuallyAppliedElements] します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-184">If you are looking for computed CSS properties, navigate to [Computed][DevtoolsCssReferenceViewActuallyAppliedElements] panel.</span></span>  

<span data-ttu-id="d69c2-185">一部のアクセシビリティ プロパティは、ブラウザーによって動的に計算されます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-185">Some accessibility properties are dynamically calculated by the browser.</span></span>  <span data-ttu-id="d69c2-186">これらのプロパティは、[アクセシビリティ] パネル **の [計算されたプロパティ** ] **セクションに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-186">These properties are displayed in the **Computed Properties** section of the **Accessibility** panel.</span></span>  

<span data-ttu-id="d69c2-187">[アクセシビリティ] パネルで、要素の計算されたアクセシビリティ プロパティ [を表示](#the-accessibility-panel) します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-187">View the computed accessibility properties of an element in the [Accessibility](#the-accessibility-panel) panel.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="[アクセシビリティ] パネルの [計算されたプロパティ] セクション" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   <span data-ttu-id="d69c2-189">[ **アクセシビリティ] パネルの** [ **計算されたプロパティ]** セクション</span><span class="sxs-lookup"><span data-stu-id="d69c2-189">The **Computed Properties** section of the **Accessibility** panel</span></span>  
:::image-end:::  

## <a name="view-the-contrast-ratio-of-a-text-element-in-the-color-picker"></a><span data-ttu-id="d69c2-190">Color Picker でテキスト要素のコントラスト比を表示する</span><span class="sxs-lookup"><span data-stu-id="d69c2-190">View the contrast ratio of a text element in the Color Picker</span></span>  

<span data-ttu-id="d69c2-191">視力の低い人の中には、領域が非常に明るい、または非常に暗いと見なされない人もいます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-191">Some people with low vision do not see areas as very bright or very dark.</span></span>  <span data-ttu-id="d69c2-192">すべてが同じ明るさで表示される傾向があります。これにより、アウトラインとエッジを区別するのは難しくなる。</span><span class="sxs-lookup"><span data-stu-id="d69c2-192">Everything tends to appear at about the same brightness, which makes it hard to distinguish outlines and edges.</span></span>  

<span data-ttu-id="d69c2-193">コントラスト比は、テキストの前景と背景の明るさの差を測定します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-193">Contrast ratio measures the difference in brightness between the foreground and background of text.</span></span>  <span data-ttu-id="d69c2-194">テキストのコントラスト比が低い場合、これらの低ビジョン ユーザーは文字通りサイトを空白の画面として表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d69c2-194">If your text has a low contrast ratio, then these low vision users may literally experience your site as a blank screen.</span></span>  

<span data-ttu-id="d69c2-195">カラー ピッカーを使用すると、テキストが推奨されるコントラスト比レベルを満たしているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-195">The Color Picker helps you verify that your text meets recommended contrast ratio levels:</span></span>  

1.  <span data-ttu-id="d69c2-196">[要素] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-196">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="d69c2-197">DOM ツリー **で、** 検査するテキスト要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-197">In the **DOM Tree**, select the text element that you want to inspect.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="DOM ツリーで段落を検査する" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       <span data-ttu-id="d69c2-199">DOM ツリーで段落を **検査する**</span><span class="sxs-lookup"><span data-stu-id="d69c2-199">Inspect a paragraph in the **DOM Tree**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d69c2-200">[スタイル **] パネル** で、要素の値の横にある `color` 色の四角形を選択します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-200">In the **Styles** panel, choose the color square next to the `color` value of the element.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="要素の color プロパティ" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       <span data-ttu-id="d69c2-202">要素 `color` のプロパティ</span><span class="sxs-lookup"><span data-stu-id="d69c2-202">The `color` property of the element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d69c2-203">カラー ピ **ッカーの [** コントラスト比] セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-203">Check the **Contrast Ratio** section of the Color Picker.</span></span>  <span data-ttu-id="d69c2-204">1 つのチェックマークは、要素が最小推奨事項を満 [たしているという意味です][W3CContrastMinimum]。</span><span class="sxs-lookup"><span data-stu-id="d69c2-204">One checkmark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span></span>  <span data-ttu-id="d69c2-205">2 つのチェック マークは、強化された推奨事項を満 [たしています][W3CContrastEnhanced]。</span><span class="sxs-lookup"><span data-stu-id="d69c2-205">Two checkmarks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="カラー ピッカーの [コントラスト比] セクションには、2 つのチェックマークと 13.97 の値が表示されます。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       <span data-ttu-id="d69c2-207">カラー **ピッカーの** [コントラスト比] セクションには、2 つのチェックマークと値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-207">The **Contrast Ratio** section of the Color Picker shows 2 checkmarks and a value of</span></span> `13.97`  
    :::image-end:::  
    
1.  <span data-ttu-id="d69c2-208">詳細については、[コントラスト比] **セクションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d69c2-208">For more information, choose the **Contrast Ratio** section.</span></span>  <span data-ttu-id="d69c2-209">カラー ピッカーの上部にあるビジュアル ピッカーに線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-209">A line appears in the visual picker at the top of the Color Picker.</span></span>  <span data-ttu-id="d69c2-210">現在の色が推奨事項を満たす場合、行の同じ側にあるものも推奨事項を満たします。</span><span class="sxs-lookup"><span data-stu-id="d69c2-210">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span></span>  <span data-ttu-id="d69c2-211">現在の色が推奨事項を満たしていない場合、同じ側にあるものも推奨事項を満たしません。</span><span class="sxs-lookup"><span data-stu-id="d69c2-211">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="ビジュアル ピッカーのコントラスト比線" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       <span data-ttu-id="d69c2-213">ビジュアル **ピッカーの** コントラスト比線</span><span class="sxs-lookup"><span data-stu-id="d69c2-213">The **Contrast Ratio** Line in the visual picker</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d69c2-214">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d69c2-214">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "支援Microsoft Edgeを使用して DevTools を操作|Microsoft Docs"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "要素に実際に適用される CSS のみを表示する - CSS リファレンス |Microsoft Docs"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe - Web アクセシビリティ テスト - Chrome ウェブストア"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "アクセシビリティ ツリー (AOM) |MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "アクセシビリティ |MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "スクリーン リーダー |MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "コントラスト (拡張) レベル AAA |W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "コントラスト (最小) レベル AA |W3C"  

> [!NOTE]
> <span data-ttu-id="d69c2-223">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="d69c2-223">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d69c2-224">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="d69c2-224">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="d69c2-226">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="d69c2-226">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
