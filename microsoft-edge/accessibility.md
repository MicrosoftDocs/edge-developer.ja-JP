---
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
description: Microsoft Edge でアクセシビリティの高い web サイトを構築、設計、テストする方法について説明します。
title: アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセシビリティ対応の web サイト、edge、web 開発、ARIA、開発者、UIA、UI オートメーション
ms.openlocfilehash: 6ad95e9c250aa6a4a61ca09470cea86efd715427
ms.sourcegitcommit: 9169d784485e3cb0b1987a8f395c4bb688bd9b2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "10583106"
---
# <span data-ttu-id="6cd09-104">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="6cd09-104">Accessibility</span></span>  

> <span data-ttu-id="6cd09-105">"\ [T/] 障碍の影響は、web 上で大幅に変更されています。 web では、世界中の多くのユーザーがコミュニケーションや操作の障壁を取り除きます。"</span><span class="sxs-lookup"><span data-stu-id="6cd09-105">"\[T\]he impact of disability is radically changed on the Web because the Web removes barriers to communication and interaction that many people face in the physical world."</span></span> [<span data-ttu-id="6cd09-106">(アクセシビリティ |勧告</span><span class="sxs-lookup"><span data-stu-id="6cd09-106">(Accessibility | W3C)</span></span>][W3CAccessibility]  

<span data-ttu-id="6cd09-107">[世界中の正常性組織][WHODisabilities]では、障碍は "ユーザーの身体の機能と、そのユーザーが住んでいる環境の機能との相互作用の不一致" として定義されています。</span><span class="sxs-lookup"><span data-stu-id="6cd09-107">The [World Health Organization][WHODisabilities] defines disability as "a mismatch in interaction between the features of a person's body and the features of the environment in which they live".</span></span>  <span data-ttu-id="6cd09-108">障碍のある方が、スマートフォンで赤ちゃんや鮮やかな日光を持っている場合や、その他の物理的、聴覚、視覚、または年齢に障碍がある場合など、さまざまな状況障碍があります。</span><span class="sxs-lookup"><span data-stu-id="6cd09-108">Disabilities range from situational disabilities, like limited mobility while holding a baby or bright sunlight on a phone, to other physical, auditory, visual, or age-related impairments.</span></span>  

<span data-ttu-id="6cd09-109">Web サイトやその他のテクノロジを設計すると、すべてのユーザーが楽しめるようになります。</span><span class="sxs-lookup"><span data-stu-id="6cd09-109">Designing websites and other technologies for inclusion creates an experience enjoyable by every person.</span></span>  <span data-ttu-id="6cd09-110">包括的なデザインと web アクセシビリティにより、すべてのユーザーが web を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6cd09-110">Inclusive design and web accessibility empowers and assists everyone to use the web.</span></span>  

<span data-ttu-id="6cd09-111">Microsoft Edge でのアクセシビリティ対応の web サイトの[設計][AccessibilityDesign]、[構築][AccessibilityBuild]、[テスト][AccessibilityTest]の詳細については、以下のベストプラクティス、コードサンプル、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cd09-111">Here are some best practices, code samples, and further resources for you to learn more about [Designing][AccessibilityDesign], [Building][AccessibilityBuild], and [Testing][AccessibilityTest] accessible websites in Microsoft Edge.</span></span>  

## <span data-ttu-id="6cd09-112">Microsoft Edge でのアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="6cd09-112">Accessibility in Microsoft Edge</span></span>  

<span data-ttu-id="6cd09-113">Microsoft Edge では、最新の[UI オートメーション API][WindowsWin32AutoEntryui] \ (UIA API \) が導入されました。</span><span class="sxs-lookup"><span data-stu-id="6cd09-113">In Microsoft Edge, we introduced modern [UI Automation API][WindowsWin32AutoEntryui] \(UIA API\).</span></span>  <span data-ttu-id="6cd09-114">UIA への変更は、ブラウザーのアクセシビリティに大きな投資となっており、Windows 10 の支援技術に依存するユーザーを対象とした、より包括的な web エクスペリエンスの基盤となっています。</span><span class="sxs-lookup"><span data-stu-id="6cd09-114">The change to UIA was a major investment in browser accessibility, and it lays the foundation for a more inclusive web experience for users who depend on assistive technology in Windows 10.</span></span>  <span data-ttu-id="6cd09-115">ユーザーは、Chromium エンジンの evergreen な性質を利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cd09-115">Users also benefit from the evergreen nature of the Chromium engine.</span></span>  

<span data-ttu-id="6cd09-116">Microsoft Edge のアクセシビリティシステムでは、ARIA、HTML5、CSS3 などの先進の web 標準がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6cd09-116">The accessibility system in Microsoft Edge inherently supports modern web standards including ARIA, HTML5, and CSS3.</span></span>  <span data-ttu-id="6cd09-117">簡略化されたブラウザパイプラインの次の図は、アクセシビリティの高いプレゼンテーション層に web ページのコンテンツを表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6cd09-117">The following diagram of the simplified browser pipeline follows webpage content into an accessible presentation layer.</span></span>  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="エンジンモデルに変換されたコンテンツは、視覚的またはアクセシビリティの高いプレゼンテーションとして表示されるビジュアルとアクセシビリティビューに投影されます。":::
   <span data-ttu-id="6cd09-119">図 1. </span><span class="sxs-lookup"><span data-stu-id="6cd09-119">Figure 1.</span></span>  <span data-ttu-id="6cd09-120">エンジンモデルに変換されたコンテンツは、視覚的またはアクセシビリティの高いプレゼンテーションとして表示されるビジュアルとアクセシビリティビューに投影されます。</span><span class="sxs-lookup"><span data-stu-id="6cd09-120">Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation</span></span>
:::image-end:::

<!--![Figure 1.  Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation][ImageAccessibilityArchitecture]  -->  

<span data-ttu-id="6cd09-121">Microsoft Edge チームは、W3C およびその他のブラウザーベンダーと継続的に協力して、新しい web プラットフォーム機能に十分なアクセシビリティが組み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cd09-121">The Microsoft Edge team works with the W3C and other browser vendors on an ongoing basis to ensure that new web platform features have sufficient built-in accessibility.</span></span>  

<span data-ttu-id="6cd09-122">Microsoft Edge でサポートされている新しい HTML5 機能の accessibly については、 [HTML5Accessibility][HTML5Accessibility]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cd09-122">For information on which new HTML5 features are accessibly supported by Microsoft Edge, visit [HTML5Accessibility][HTML5Accessibility].</span></span>  

## <span data-ttu-id="6cd09-123">リソース</span><span class="sxs-lookup"><span data-stu-id="6cd09-123">Resources</span></span>  

#### <span data-ttu-id="6cd09-124">Microsoft Windows UI Automation ブログ</span><span class="sxs-lookup"><span data-stu-id="6cd09-124">Microsoft Windows UI Automation Blog</span></span>  

<span data-ttu-id="6cd09-125">[Microsoft WINDOWS UI オートメーションのブログ][ArchiveBlogsWinuiautomation]では、WINDOWS オートメーション API に関連するトピックを取り上げています。</span><span class="sxs-lookup"><span data-stu-id="6cd09-125">The [Microsoft Windows UI Automation blog][ArchiveBlogsWinuiautomation] covers topics related to the Windows Automation API.</span></span>  

#### <span data-ttu-id="6cd09-126">Web アクセシビリティイニシアチブ (WAI-ARIA 使った)</span><span class="sxs-lookup"><span data-stu-id="6cd09-126">Web Accessibility Initiative (WAI)</span></span>  

<span data-ttu-id="6cd09-127">Bt である[Web アクセシビリティイニシアチブ (wai-aria 使った)][W3CWaiHome]は、web のアクセシビリティを向上させるための取り組みとなっています。</span><span class="sxs-lookup"><span data-stu-id="6cd09-127">The [Web Accessibility Initiative (WAI)][W3CWaiHome] provided bt the W3C is an effort to help improve the accessibility of the web.</span></span>  <span data-ttu-id="6cd09-128">このサイトには、 [Web アクセシビリティの使用を開始][W3CWaiGettingstartedOverview]するためのさまざまなリソースが用意されています。また、[追加][W3CWaiFundamentals]、[チュートリアル、プレゼンテーション][W3CWaiTeachAdvocate]などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6cd09-128">The site provides a variety of resources for [Getting Started with Web Accessibility][W3CWaiGettingstartedOverview], [Designing for Inclusion][W3CWaiFundamentals], [tutorials and presentations][W3CWaiTeachAdvocate], and more.</span></span>  


<!-- image links -->  

<!--[ImageAccessibilityArchitecture]: ./media/accessibilityarchitecture.png "Figure 1: Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation"  -->  

<!-- links -->  

[AccessibilityBuild]: ./accessibility/build.md "アクセシビリティの高い Web サイトを構築する"  
[AccessibilityDesign]: ./accessibility/design.md "アクセシビリティの高い Web サイトを設計する"  
[AccessibilityTest]: ./accessibility/test.md "アクセシビリティテスト"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI オートメーション"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI Automation ブログ"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 のアクセシビリティ"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "アクセシビリティ |勧告"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web アクセシビリティの概要 |Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "はじめに: Web サイトのアクセシビリティを向上させる |Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  
[W3CWaiHome]: https://w3.org/wai "Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "講義と代弁の概要 |Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  

[WHODisabilities]: https://who.int/topics/disabilities "障碍 |誰が"  

