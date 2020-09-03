---
description: Microsoft Edge DevTools のアクセシビリティ機能の包括的な参照。
title: アクセシビリティリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 39b0b8c36cea017b9976ea4e80e92ea93896a671
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993269"
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

# <span data-ttu-id="1cd96-104">アクセシビリティリファレンス</span><span class="sxs-lookup"><span data-stu-id="1cd96-104">Accessibility reference</span></span>  

<span data-ttu-id="1cd96-105">このページでは、Microsoft Edge DevTools のアクセシビリティ機能の包括的な参照を示します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-105">This page is a comprehensive reference of accessibility features in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="1cd96-106">これは、次のような web 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="1cd96-106">It is intended for web developers who:</span></span>  

*   <span data-ttu-id="1cd96-107">アプリを開く方法など、DevTools の基本を理解している。</span><span class="sxs-lookup"><span data-stu-id="1cd96-107">Have a basic understanding of DevTools, such as how to open it.</span></span>  
*   <span data-ttu-id="1cd96-108">[アクセシビリティの原則とベストプラクティス][MDNAccessibility]について理解している。</span><span class="sxs-lookup"><span data-stu-id="1cd96-108">Are familiar with [accessibility principles and best practices][MDNAccessibility].</span></span>  
    
<span data-ttu-id="1cd96-109">このリファレンスの目的は、ページのアクセシビリティを確認するのに役立つ DevTools で利用可能なすべてのツールを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-109">The purpose of this reference is to help you discover all of the tools available in DevTools that help you examine the accessibility of a page.</span></span>  

<span data-ttu-id="1cd96-110">スクリーンリーダーなどの支援技術を利用して DevTools を操作する方法については、「 [Microsoft Edge DevTools を支援技術でナビゲート][DevtoolsAccessibilityNavigation] する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd96-110">See [Navigating Microsoft Edge DevTools With Assistive Technology][DevtoolsAccessibilityNavigation] if you are looking for help on navigating DevTools with an assistive technology like a screen reader.</span></span>  

## <span data-ttu-id="1cd96-111">Microsoft Edge DevTools のアクセシビリティ機能の概要</span><span class="sxs-lookup"><span data-stu-id="1cd96-111">Overview of accessibility features in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="1cd96-112">このセクションでは、DevTools が全体的なアクセシビリティツールキットにどのように適合するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-112">This section explains how DevTools fits into your overall accessibility toolkit.</span></span>  

<span data-ttu-id="1cd96-113">ページにアクセスできるかどうかを判断する際には、次の2つの一般的な質問に留意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd96-113">When determining whether a page is accessible, you need to have 2 general questions in mind:</span></span>  

1.  <span data-ttu-id="1cd96-114">キーボードまたは [スクリーンリーダー][MDNScreenReader]を使用してページ内を移動することはできますか?</span><span class="sxs-lookup"><span data-stu-id="1cd96-114">Are you able to navigate the page with a keyboard or [screen reader][MDNScreenReader]?</span></span>  
1.  <span data-ttu-id="1cd96-115">ページの要素は、スクリーンリーダー用に適切にマークされていますか。</span><span class="sxs-lookup"><span data-stu-id="1cd96-115">Are the elements of the page properly marked up for screen readers?</span></span>  
    
<span data-ttu-id="1cd96-116">一般的に、DevTools は、#2 質問に関連するエラーを解決するのに役立ちます。これらのエラーは、自動的な方法で簡単に検出することができます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-116">In general, DevTools should help you fix errors related to question #2, because these errors are easy to detect in an automated fashion.</span></span>  <span data-ttu-id="1cd96-117">質問 #1 は重要ですが、残念ながら、このツールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cd96-117">Question #1 is just as important, but unfortunately DevTools does not help you there.</span></span>  <span data-ttu-id="1cd96-118">#1 質問に関連するエラーを見つけるには、自分でキーボードまたはスクリーンリーダーを使用してページを使用する方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="1cd96-118">The only way to find errors related to question #1 is to try using a page with a keyboard or screen reader yourself.</span></span>  <!--See [How To Do An Accessibility Review][AccessibilityReview] to learn more.  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <span data-ttu-id="1cd96-119">ページのアクセシビリティを監査する</span><span class="sxs-lookup"><span data-stu-id="1cd96-119">Audit the accessibility of a page</span></span>  

> [!NOTE]
> <span data-ttu-id="1cd96-120">**監査**パネルは、サードパーティの web サイトでホストされているコンテンツへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-120">The **Audits** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="1cd96-121">Microsoft は、これらのサイトのコンテンツおよび収集される可能性のあるデータを管理する責任を負いません。</span><span class="sxs-lookup"><span data-stu-id="1cd96-121">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span></span>  

<span data-ttu-id="1cd96-122">一般的に、監査パネルを使用して、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-122">In general, use the Audits panel to determine if:</span></span>  

*   <span data-ttu-id="1cd96-123">ページには、スクリーンリーダーのマークが正しく設定されています。</span><span class="sxs-lookup"><span data-stu-id="1cd96-123">A page is properly marked up for screen readers.</span></span>  
*   <span data-ttu-id="1cd96-124">ページ上のテキスト要素には、十分なコントラスト率があります。</span><span class="sxs-lookup"><span data-stu-id="1cd96-124">The text elements on a page have sufficient contrast ratios.</span></span>  <span data-ttu-id="1cd96-125">「 [カラーピッカーのテキスト要素のコントラスト比を表示する](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd96-125">See [View the contrast ratio of a text element in the Color Picker](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker).</span></span>  

<span data-ttu-id="1cd96-126">ページを監査するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1cd96-126">To audit a page:</span></span>  

1.  <span data-ttu-id="1cd96-127">監査する URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-127">Go to the URL that you want to audit.</span></span>  
1.  <span data-ttu-id="1cd96-128">DevTools で、[ **監査** ] タブをクリックします。 DevTools には、さまざまな構成オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-128">In DevTools, click the **Audits** tab.  DevTools shows you various configuration options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="監査を構成する" lightbox="../media/accessibility-audits-pane.msft.png":::
       <span data-ttu-id="1cd96-130">監査を構成する</span><span class="sxs-lookup"><span data-stu-id="1cd96-130">Configure audits</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="1cd96-131">このセクションのスクリーンショットは、Microsoft Edge のバージョン79で採用されています。</span><span class="sxs-lookup"><span data-stu-id="1cd96-131">The screenshots in this section were taken with version 79 of Microsoft Edge.</span></span>  <span data-ttu-id="1cd96-132">実行しているバージョンを確認でき `edge://version` ます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-132">You may check what version you are running at `edge://version`.</span></span>  <span data-ttu-id="1cd96-133">**監査**パネルの UI は、以前のバージョンの Microsoft Edge では異なりますが、一般的なワークフローは同じです。</span><span class="sxs-lookup"><span data-stu-id="1cd96-133">The **Audits** panel UI looks different in earlier versions of Microsoft Edge, but the general workflow is the same.</span></span>  
    
1.  <span data-ttu-id="1cd96-134">モバイルデバイスをシミュレートする場合は、[ **デバイス**] で [ **モバイル** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-134">For **Device**, select **Mobile** if you want to simulate a mobile device.</span></span>  <span data-ttu-id="1cd96-135">このオプションでは、ユーザーエージェントの文字列が変更され、ビューポートのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-135">This option changes your user agent string and resizes the viewport.</span></span>  <span data-ttu-id="1cd96-136">ページのモバイルバージョンの表示がデスクトップバージョンとは異なる場合、このオプションは監査結果に大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cd96-136">If the mobile version of the page displays differently than the desktop version, this option could have a significant effect on the results of your audit.</span></span>  
1.  <span data-ttu-id="1cd96-137">[ **監査** ] セクションで、[ **アクセシビリティ** ] が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-137">In the **Audits** section, make sure that **Accessibility** is enabled.</span></span>  <span data-ttu-id="1cd96-138">レポートから除外する場合は、その他のカテゴリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-138">Disable the other categories if you want to exclude them from your report.</span></span>  <span data-ttu-id="1cd96-139">ページの品質を向上させるその他の方法を見つける場合は、有効のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-139">Leave them enabled if you want to discover other ways to improve the quality of your page.</span></span>  
1.  <span data-ttu-id="1cd96-140">[ **調整** ] セクションでは、ネットワークと CPU を調整することができます。これは、読み込みのパフォーマンスを分析するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-140">The **Throttling** section lets you throttle the network and CPU, which is useful when analyzing load performance.</span></span>  <span data-ttu-id="1cd96-141">このオプションは、お客様のアクセシビリティのスコアには無関係であるため、好きなように使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-141">This option should be irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="1cd96-142">[ **記憶域のクリア** ] チェックボックスを使用すると、ページを読み込む前にすべての記憶域をクリアするか、ページの読み込みの間に記憶域を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-142">The **Clear Storage** checkbox lets you clear all storage before loading the page, or preserve storage between page loads.</span></span>  <span data-ttu-id="1cd96-143">このオプションは、アクセシビリティのスコアには無関係であるため、好きなように使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-143">This option is also probably irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="1cd96-144">[ **監査の実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-144">Click **Run Audits**.</span></span> <span data-ttu-id="1cd96-145">10 ~ 30 秒後に、DevTools でレポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-145">After 10 to 30 seconds, DevTools provides a report.</span></span>  <span data-ttu-id="1cd96-146">レポートには、ページのアクセシビリティを向上させるためのさまざまなヒントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1cd96-146">Your report gives you various tips on how to improve the accessibility of the page.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="レポート" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       <span data-ttu-id="1cd96-148">レポート</span><span class="sxs-lookup"><span data-stu-id="1cd96-148">A report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1cd96-149">詳細については、監査をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="1cd96-149">Click an audit to learn more about it.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="監査に関するその他の情報" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       <span data-ttu-id="1cd96-151">監査に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="1cd96-151">More information about an audit</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1cd96-152">[ **詳細情報** ] をクリックして、その監査のドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-152">Click **Learn More** to view the documentation of that audit.</span></span>  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="監査のドキュメントを表示する" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       <span data-ttu-id="1cd96-154">監査のドキュメントを表示する</span><span class="sxs-lookup"><span data-stu-id="1cd96-154">View the documentation of an audit</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="1cd96-155">「アックス extension」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1cd96-155">See also: aXe extension</span></span>  

<span data-ttu-id="1cd96-156">**監査**パネルではなく、[アックスの拡張機能][ChromeWebStoreAxe]を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-156">You may prefer to use the [aXe extension][ChromeWebStoreAxe] rather than the **Audits** panel.</span></span>  
<span data-ttu-id="1cd96-157">通常、アックス extension は、監査パネルを累乗する基になるエンジンであるため、同じ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-157">The aXe extension generally provides the same information, since it is the underlying engine that powers the Audits panel.</span></span>  <span data-ttu-id="1cd96-158">アックス extension にはさまざまな UI があり、監査の方法は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="1cd96-158">The aXe extension has a different UI and describes audits slightly differently.</span></span>  
<span data-ttu-id="1cd96-159">[ **監査** ] パネルに表示される [アックス extension] の利点の1つは、障害のあるノードを検査して強調表示できることです。</span><span class="sxs-lookup"><span data-stu-id="1cd96-159">One advantage that the aXe extension has over the **Audits** panel is that it enables you to inspect and highlight failing nodes.</span></span>  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="アックス extension" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   <span data-ttu-id="1cd96-161">アックス extension</span><span class="sxs-lookup"><span data-stu-id="1cd96-161">The aXe extension</span></span>  
:::image-end:::  

## <span data-ttu-id="1cd96-162">[アクセシビリティ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1cd96-162">The Accessibility pane</span></span>  

<span data-ttu-id="1cd96-163">[ **アクセシビリティ** ] ウィンドウは、DOM ノードのアクセシビリティツリー、ARIA 属性、および計算されたアクセシビリティプロパティを表示する場所です。</span><span class="sxs-lookup"><span data-stu-id="1cd96-163">The **Accessibility** pane is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span></span>  

<span data-ttu-id="1cd96-164">[ **アクセシビリティ** ] ウィンドウを開くには:</span><span class="sxs-lookup"><span data-stu-id="1cd96-164">To open the **Accessibility** pane:</span></span>  

1.  <span data-ttu-id="1cd96-165">[ **要素** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-165">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="1cd96-166">**DOM ツリー**で、検査する要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-166">In the **DOM Tree**, select the element which you want to inspect.</span></span>  
1.  <span data-ttu-id="1cd96-167">[ **アクセシビリティ** ] タブをクリックします。 このタブは、[ **その他** のタブ \ ( ![ その他のタブ)] ボタンの背後に隠れている可能性があり ][ImageMoreTabsIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-167">Click the **Accessibility** tab.  This tab may be hidden behind the **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) button.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="[アクセシビリティ] ウィンドウで DevTools ホームページの h1 要素を検査する" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   <span data-ttu-id="1cd96-169">[ `h1` **アクセシビリティ** ] ウィンドウで devtools ホームページの要素を検査する</span><span class="sxs-lookup"><span data-stu-id="1cd96-169">Inspect the `h1` element of the DevTools homepage in the **Accessibility** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="1cd96-170">アクセシビリティツリーの要素の位置を表示する</span><span class="sxs-lookup"><span data-stu-id="1cd96-170">View the position of an element in the accessibility tree</span></span>  

<span data-ttu-id="1cd96-171">[アクセシビリティツリー][MDNAccessibilityTree]は DOM ツリーのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="1cd96-171">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span></span>  <span data-ttu-id="1cd96-172">DOM ツリーの要素のみが含まれます。これには、スクリーンリーダーでページのコンテンツを表示するために役立つ、関連する有用な要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1cd96-172">It only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span></span>  

<span data-ttu-id="1cd96-173">アクセシビリティツリーの要素の位置を [ [アクセシビリティ] ウィンドウ](#the-accessibility-pane)から調べます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-173">Inspect the position of an element in the accessibility tree from the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="[アクセシビリティツリー] セクション" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   <span data-ttu-id="1cd96-175">[ **アクセシビリティツリー** ] セクション</span><span class="sxs-lookup"><span data-stu-id="1cd96-175">The **Accessibility Tree** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1cd96-176">要素の ARIA 属性を表示する</span><span class="sxs-lookup"><span data-stu-id="1cd96-176">View the ARIA attributes of an element</span></span>  

<span data-ttu-id="1cd96-177">ARIA 属性によって、ページのコンテンツを適切に表すために必要なすべての情報をスクリーンリーダーに確実に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-177">ARIA attributes ensure that screen readers have all of the information that they need in order to properly represent the contents of a page.</span></span>  

<span data-ttu-id="1cd96-178">[ [アクセシビリティ] ウィンドウ](#the-accessibility-pane)で要素の ARIA 属性を表示します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-178">View the ARIA attributes of an element in the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="[ARIA 属性] セクション" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   <span data-ttu-id="1cd96-180">[ **ARIA 属性** ] セクション</span><span class="sxs-lookup"><span data-stu-id="1cd96-180">The **ARIA Attributes** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1cd96-181">要素の計算されたアクセシビリティプロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="1cd96-181">View the computed accessibility properties of an element</span></span>  

> [!NOTE]
> <span data-ttu-id="1cd96-182">計算された CSS プロパティを検索する場合は、[ [計算] タブ][DevtoolsCssReferenceViewActuallyAppliedElements]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd96-182">If you are looking for computed CSS properties, see the [Computed tab][DevtoolsCssReferenceViewActuallyAppliedElements].</span></span>  

<span data-ttu-id="1cd96-183">一部のアクセシビリティプロパティは、ブラウザーによって動的に計算されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-183">Some accessibility properties are dynamically calculated by the browser.</span></span>  <span data-ttu-id="1cd96-184">これらのプロパティは、[**アクセシビリティ**] ウィンドウの [計算された**プロパティ**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-184">These properties are displayed in the **Computed Properties** section of the **Accessibility** pane.</span></span>  

<span data-ttu-id="1cd96-185">[ [アクセシビリティ] ウィンドウ](#the-accessibility-pane)で、要素の計算されたアクセシビリティプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-185">View the computed accessibility properties of an element in the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="[アクセシビリティ] ウィンドウの [計算されたプロパティ] セクション" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   <span data-ttu-id="1cd96-187">[**アクセシビリティ**] ウィンドウの [計算された**プロパティ**] セクション</span><span class="sxs-lookup"><span data-stu-id="1cd96-187">The **Computed Properties** section of the **Accessibility** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="1cd96-188">カラーピッカーでのテキスト要素のコントラスト比の表示</span><span class="sxs-lookup"><span data-stu-id="1cd96-188">View the contrast ratio of a text element in the Color Picker</span></span>  

<span data-ttu-id="1cd96-189">視覚障碍のあるユーザーは、領域を非常に明るく、または非常に暗くします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-189">Some people with low vision do not see areas as very bright or very dark.</span></span>  <span data-ttu-id="1cd96-190">すべての機能が同じ輝度で表示される傾向があります。これにより、アウトラインとエッジを区別しにくくなります。</span><span class="sxs-lookup"><span data-stu-id="1cd96-190">Everything tends to appear at about the same brightness, which makes it hard to distinguish outlines and edges.</span></span>  

<span data-ttu-id="1cd96-191">コントラスト比は、テキストの前景と背景の間の輝度の差を測定します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-191">Contrast ratio measures the difference in brightness between the foreground and background of text.</span></span>  <span data-ttu-id="1cd96-192">テキストのコントラスト比が低い場合、これらの視覚に障碍があるユーザーは、文字どおり空の画面としてサイトを表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cd96-192">If your text has a low contrast ratio, then these low vision users may literally experience your site as a blank screen.</span></span>  

<span data-ttu-id="1cd96-193">カラーピッカーは、テキストが推奨されるコントラスト比レベルを満たしているかどうかを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-193">The Color Picker helps you verify that your text meets recommended contrast ratio levels:</span></span>  

1.  <span data-ttu-id="1cd96-194">[ **要素** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-194">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="1cd96-195">**DOM ツリー**で、検査するテキスト要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-195">In the **DOM Tree**, select the text element that you want to inspect.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="DOM ツリーの段落を検査する" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       <span data-ttu-id="1cd96-197">**DOM ツリー**の段落を検査する</span><span class="sxs-lookup"><span data-stu-id="1cd96-197">Inspect a paragraph in the **DOM Tree**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1cd96-198">[ **スタイル** ] ウィンドウで、要素の値の横にある色の四角をクリックし `color` ます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-198">In the **Styles** pane, click the color square next to the `color` value of the element.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="要素の color プロパティ" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       <span data-ttu-id="1cd96-200">`color`要素のプロパティ</span><span class="sxs-lookup"><span data-stu-id="1cd96-200">The `color` property of the element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1cd96-201">カラーピッカーの [ **コントラスト比** ] のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-201">Check the **Contrast Ratio** section of the Color Picker.</span></span>  <span data-ttu-id="1cd96-202">1つのチェックマークは、要素が [最小要件][W3CContrastMinimum]を満たしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-202">One checkmark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span></span>  <span data-ttu-id="1cd96-203">2つのチェックマークは、強化された [推奨事項][W3CContrastEnhanced]を満たしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-203">Two checkmarks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="カラーピッカーの [コントラスト比] セクションには、2つのチェックマークと値13.97 が表示されます。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       <span data-ttu-id="1cd96-205">カラーピッカーの [ **コントラスト比** ] セクションには、2つのチェックマークと値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-205">The **Contrast Ratio** section of the Color Picker shows 2 checkmarks and a value of</span></span> `13.97`  
    :::image-end:::  
    
1.  <span data-ttu-id="1cd96-206">[ **コントラスト比** ] セクションをクリックして、詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1cd96-206">Click the **Contrast Ratio** section to see more information.</span></span>  <span data-ttu-id="1cd96-207">カラーピッカーの上部にあるビジュアルピッカーに線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-207">A line appears in the visual picker at the top of the Color Picker.</span></span>  <span data-ttu-id="1cd96-208">現在の色が推奨事項を満たしている場合は、その行の同じ側にあるものも、推奨事項を満たしているものとします。</span><span class="sxs-lookup"><span data-stu-id="1cd96-208">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span></span>  <span data-ttu-id="1cd96-209">現在の色が推奨事項を満たしていない場合は、同じ側にあるものも、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="1cd96-209">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="ビジュアルピッカーのコントラスト比線" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       <span data-ttu-id="1cd96-211">ビジュアルピッカーの **コントラスト比** 線</span><span class="sxs-lookup"><span data-stu-id="1cd96-211">The **Contrast Ratio** Line in the visual picker</span></span>  
    :::image-end:::  
    
<!--## Feedback   -->  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "支援技術を使用して Microsoft Edge DevTools を操作する |Microsoft ドキュメント"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "要素の CSS 参照に実際に適用されている CSS のみを表示します。 |Microsoft ドキュメント"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "アックス-Web アクセシビリティテスト-Chrome Web ストア"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "アクセシビリティツリー (AOM) |MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "アクセシビリティ |MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "スクリーンリーダー |MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "コントラスト (強化) レベル AAA |勧告"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "コントラスト (最小) レベル AA |勧告"  

> [!NOTE]
> <span data-ttu-id="1cd96-220">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cd96-220">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1cd96-221">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="1cd96-221">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1cd96-223">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1cd96-223">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
