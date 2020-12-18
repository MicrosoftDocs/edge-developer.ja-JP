---
description: Microsoft Edge 内でアクセス可能な Web サイトを構築、設計、テストする方法について説明します。
title: アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
keywords: アクセシビリティ, 開発者向けアクセシビリティ, アクセシビリティ対応の Web サイト, エッジ, Web 開発, ARIA, 開発者, UIA, UI オートメーション
ms.openlocfilehash: ae2b0a876b60e0475e283cc52ffd14275fc32aba
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234502"
---
# <span data-ttu-id="2c98b-104">アクセシビリティの概要</span><span class="sxs-lookup"><span data-stu-id="2c98b-104">Accessibility overview</span></span>  

> <span data-ttu-id="2c98b-105">"\[T\]障がいへの影響は、Web 上で根本的に変更されています。Web は、多くのユーザーが物理的な世界で直面する通信とやり取りに対する障壁を取り除くからです。"</span><span class="sxs-lookup"><span data-stu-id="2c98b-105">"\[T\]he impact of disability is radically changed on the Web because the Web removes barriers to communication and interaction that many people face in the physical world."</span></span> [<span data-ttu-id="2c98b-106">(アクセシビリティ |W3C)</span><span class="sxs-lookup"><span data-stu-id="2c98b-106">(Accessibility | W3C)</span></span>][W3CAccessibility]  

<span data-ttu-id="2c98b-107">世界 [保健機関][WHODisabilities] は、障がいを 「身体の機能と、その人が住んでいる環境の機能との相互作用の不一致」と定義しています。</span><span class="sxs-lookup"><span data-stu-id="2c98b-107">The [World Health Organization][WHODisabilities] defines disability as "a mismatch in interaction between the features of a person's body and the features of the environment in which they live".</span></span>  <span data-ttu-id="2c98b-108">障がいを持っている場合は、限られた運動障がいを持ちながら携帯電話に光を当て、その他の物理的、監査、視覚、または年齢に関連する障がいがあります。</span><span class="sxs-lookup"><span data-stu-id="2c98b-108">Disabilities range from situational disabilities, like limited mobility while holding a baby or bright sunlight on a phone, to other physical, auditory, visual, or age-related impairments.</span></span>  

<span data-ttu-id="2c98b-109">含める Web サイトや他のテクノロジを設計すると、すべてのユーザーが楽しいエクスペリエンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="2c98b-109">Designing websites and other technologies for inclusion creates an experience enjoyable by every person.</span></span>  <span data-ttu-id="2c98b-110">包括的なデザインと Web アクセシビリティにより、すべてのユーザーが Web を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c98b-110">Inclusive design and web accessibility empowers and assists everyone to use the web.</span></span>  

<span data-ttu-id="2c98b-111">Microsoft Edge でのアクセス可能な Web サイトの設計、構築、テストについて詳しくは[][AccessibilityBuild]、ベスト[][AccessibilityTest]プラクティス、コード サンプル、その他のリソースをご覧ください。 [][AccessibilityDesign]</span><span class="sxs-lookup"><span data-stu-id="2c98b-111">Here are some best practices, code samples, and further resources for you to learn more about [Designing][AccessibilityDesign], [Building][AccessibilityBuild], and [Testing][AccessibilityTest] accessible websites in Microsoft Edge.</span></span>  

## <span data-ttu-id="2c98b-112">Microsoft Edge のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="2c98b-112">Accessibility in Microsoft Edge</span></span>  

<span data-ttu-id="2c98b-113">Microsoft Edge では、最新の [UI オートメーション API][WindowsWin32AutoEntryui] \(UIA API\) を導入しました。</span><span class="sxs-lookup"><span data-stu-id="2c98b-113">In Microsoft Edge, we introduced modern [UI Automation API][WindowsWin32AutoEntryui] \(UIA API\).</span></span>  <span data-ttu-id="2c98b-114">UIA の変更は、ブラウザーのアクセシビリティに大きな投資を行い、Windows 10 の支援技術に依存するユーザーにとってより包括的な Web エクスペリエンスの基盤を構築しました。</span><span class="sxs-lookup"><span data-stu-id="2c98b-114">The change to UIA was a major investment in browser accessibility, and it lays the foundation for a more inclusive web experience for users who depend on assistive technology in Windows 10.</span></span>  <span data-ttu-id="2c98b-115">また、Chromium エンジンの常に存在する性質も利用できます。</span><span class="sxs-lookup"><span data-stu-id="2c98b-115">Users also benefit from the evergreen nature of the Chromium engine.</span></span>  

<span data-ttu-id="2c98b-116">Microsoft Edge のアクセシビリティ システムは、ARIA、HTML5、CSS3 などの最新の Web 標準を本質的にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2c98b-116">The accessibility system in Microsoft Edge inherently supports modern web standards including ARIA, HTML5, and CSS3.</span></span>  <span data-ttu-id="2c98b-117">簡素化されたブラウザー パイプラインの次の図は、Web ページのコンテンツに従って、アクセス可能なプレゼンテーション層に入ります。</span><span class="sxs-lookup"><span data-stu-id="2c98b-117">The following diagram of the simplified browser pipeline follows webpage content into an accessible presentation layer.</span></span>  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="エンジン モデルに変換されたコンテンツは、視覚的またはアクセシビリティに対応したプレゼンテーションとして表示されるビジュアル ビューとアクセシビリティ ビューに投影されます。":::
   <span data-ttu-id="2c98b-119">エンジン モデルに変換されたコンテンツは、視覚的またはアクセシビリティに対応したプレゼンテーションとして表示されるビジュアル ビューとアクセシビリティ ビューに投影されます。</span><span class="sxs-lookup"><span data-stu-id="2c98b-119">Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation</span></span>  
:::image-end:::  

<span data-ttu-id="2c98b-120">Microsoft Edge チームは、W3C や他のブラウザー ベンダーと継続的に取り組み、新しい Web プラットフォーム機能に十分な組み込みのアクセシビリティが備わっています。</span><span class="sxs-lookup"><span data-stu-id="2c98b-120">The Microsoft Edge team works with the W3C and other browser vendors on an ongoing basis to ensure that new web platform features have sufficient built-in accessibility.</span></span>  

<span data-ttu-id="2c98b-121">Microsoft Edge でサポートされている新しい HTML5 機能の詳細については [、HTML5Accessibility に移動します][HTML5Accessibility]。</span><span class="sxs-lookup"><span data-stu-id="2c98b-121">For information on which new HTML5 features are accessibly supported by Microsoft Edge, navigate to [HTML5Accessibility][HTML5Accessibility].</span></span>  

## <span data-ttu-id="2c98b-122">リソース</span><span class="sxs-lookup"><span data-stu-id="2c98b-122">Resources</span></span>  

#### <span data-ttu-id="2c98b-123">Microsoft Windows UI オートメーションに関するブログ</span><span class="sxs-lookup"><span data-stu-id="2c98b-123">Microsoft Windows UI Automation Blog</span></span>  

<span data-ttu-id="2c98b-124">[Microsoft Windows UI Automation ブログでは、Windows][ArchiveBlogsWinuiautomation]オートメーション API に関連するトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2c98b-124">The [Microsoft Windows UI Automation blog][ArchiveBlogsWinuiautomation] covers topics related to the Windows Automation API.</span></span>  

#### <span data-ttu-id="2c98b-125">Web Accessibility Initiative (INITIATIVE)</span><span class="sxs-lookup"><span data-stu-id="2c98b-125">Web Accessibility Initiative (WAI)</span></span>  

<span data-ttu-id="2c98b-126">[WEB アクセシビリティ イニシアティブ (INITIATIVE)][W3CWaiHome]が提供する bt the W3C は、Web のアクセシビリティを向上させる取り組みです。</span><span class="sxs-lookup"><span data-stu-id="2c98b-126">The [Web Accessibility Initiative (WAI)][W3CWaiHome] provided bt the W3C is an effort to help improve the accessibility of the web.</span></span>  <span data-ttu-id="2c98b-127">このサイトでは[、Web][W3CWaiGettingstartedOverview]アクセシビリティの使用の開始、包含のための設計、チュートリアル[][W3CWaiFundamentals]とプレゼンテーションなど、さまざまな[リソースが提供][W3CWaiTeachAdvocate]されています。</span><span class="sxs-lookup"><span data-stu-id="2c98b-127">The site provides a variety of resources for [Getting Started with Web Accessibility][W3CWaiGettingstartedOverview], [Designing for Inclusion][W3CWaiFundamentals], [tutorials and presentations][W3CWaiTeachAdvocate], and more.</span></span>  

<!-- links -->  

[AccessibilityBuild]: ./build/index.md "アクセス可能な Web サイトの構築 |Microsoft Doc"  
[AccessibilityDesign]: ./design.md "アクセス可能な Web サイトの設計 |Microsoft Doc"  
[AccessibilityTest]: ./test.md "アクセシビリティ テスト |Microsoft Docs"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI オートメーション |Microsoft Doc"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI オートメーションブログ |Microsoft Doc"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 アクセシビリティ"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "アクセシビリティ |W3C"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web アクセシビリティの概要 |Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "概要: Web サイトをアクセス可能にする |Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  
[W3CWaiHome]: https://w3.org/wai "Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "教えと支持者の概要 |Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  

[WHODisabilities]: https://who.int/topics/disabilities "障がい |誰が"  

