---
description: Web サイト内でアクセス可能な Web サイトを構築、設計、テストするMicrosoft Edge。
title: アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.openlocfilehash: ae2b0a876b60e0475e283cc52ffd14275fc32aba
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234502"
---
# <span data-ttu-id="f55ff-104">アクセシビリティの概要</span><span class="sxs-lookup"><span data-stu-id="f55ff-104">Accessibility overview</span></span>  

> <span data-ttu-id="f55ff-105">"\[T\]障害の影響は、Web が物理的な世界で多くの人々が直面するコミュニケーションと相互作用の障壁を取り除くので、Web 上で根本的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="f55ff-105">"\[T\]he impact of disability is radically changed on the Web because the Web removes barriers to communication and interaction that many people face in the physical world."</span></span> [<span data-ttu-id="f55ff-106">(アクセシビリティ |W3C)</span><span class="sxs-lookup"><span data-stu-id="f55ff-106">(Accessibility | W3C)</span></span>][W3CAccessibility]  

<span data-ttu-id="f55ff-107">世界 [保健機関は][WHODisabilities] 、障がいを「身体の機能と、その身体が住む環境の特徴との間の相互作用の不一致」と定義しています。</span><span class="sxs-lookup"><span data-stu-id="f55ff-107">The [World Health Organization][WHODisabilities] defines disability as "a mismatch in interaction between the features of a person's body and the features of the environment in which they live".</span></span>  <span data-ttu-id="f55ff-108">障害は、携帯電話で赤ちゃんや明るい日差しを保持している間の身体の制限など、状況の障害から、他の物理的、聴覚、視覚、または年齢に関連する障害までです。</span><span class="sxs-lookup"><span data-stu-id="f55ff-108">Disabilities range from situational disabilities, like limited mobility while holding a baby or bright sunlight on a phone, to other physical, auditory, visual, or age-related impairments.</span></span>  

<span data-ttu-id="f55ff-109">Web サイトや他のテクノロジを組み込むデザインは、すべてのユーザーが楽しめるエクスペリエンスを作り出します。</span><span class="sxs-lookup"><span data-stu-id="f55ff-109">Designing websites and other technologies for inclusion creates an experience enjoyable by every person.</span></span>  <span data-ttu-id="f55ff-110">包括的なデザインと Web アクセシビリティは、すべてのユーザーが Web を使用する権限を与え、支援します。</span><span class="sxs-lookup"><span data-stu-id="f55ff-110">Inclusive design and web accessibility empowers and assists everyone to use the web.</span></span>  

<span data-ttu-id="f55ff-111">設計、構築、およびテストのアクセス可能な Web サイトの詳細については、ベスト プラクティス[][AccessibilityBuild]、コード[][AccessibilityTest]サンプル、その他のリソースをMicrosoft Edge。 [][AccessibilityDesign]</span><span class="sxs-lookup"><span data-stu-id="f55ff-111">Here are some best practices, code samples, and further resources for you to learn more about [Designing][AccessibilityDesign], [Building][AccessibilityBuild], and [Testing][AccessibilityTest] accessible websites in Microsoft Edge.</span></span>  

## <span data-ttu-id="f55ff-112">ユーザー補助Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f55ff-112">Accessibility in Microsoft Edge</span></span>  

<span data-ttu-id="f55ff-113">このMicrosoft Edge、モダン[UI オートメーション API][WindowsWin32AutoEntryui] \(UIA API\) を導入しました。</span><span class="sxs-lookup"><span data-stu-id="f55ff-113">In Microsoft Edge, we introduced modern [UI Automation API][WindowsWin32AutoEntryui] \(UIA API\).</span></span>  <span data-ttu-id="f55ff-114">UIA への変更は、ブラウザーアクセシビリティへの大きな投資であり、Windows 10 で支援技術に依存しているユーザーにとって、より包括的な Web エクスペリエンスの基盤を築きます。</span><span class="sxs-lookup"><span data-stu-id="f55ff-114">The change to UIA was a major investment in browser accessibility, and it lays the foundation for a more inclusive web experience for users who depend on assistive technology in Windows 10.</span></span>  <span data-ttu-id="f55ff-115">また、ユーザーは、エンジンの常緑Chromiumします。</span><span class="sxs-lookup"><span data-stu-id="f55ff-115">Users also benefit from the evergreen nature of the Chromium engine.</span></span>  

<span data-ttu-id="f55ff-116">このシステムのアクセシビリティ システムMicrosoft Edge、ARIA、HTML5、CSS3 などの最新の Web 標準を本質的にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f55ff-116">The accessibility system in Microsoft Edge inherently supports modern web standards including ARIA, HTML5, and CSS3.</span></span>  <span data-ttu-id="f55ff-117">簡略化されたブラウザー パイプラインの次の図は、Web ページのコンテンツをアクセス可能なプレゼンテーション 層に従います。</span><span class="sxs-lookup"><span data-stu-id="f55ff-117">The following diagram of the simplified browser pipeline follows webpage content into an accessible presentation layer.</span></span>  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="エンジン モデルに変換されたコンテンツは、視覚的またはアクセス可能なプレゼンテーションとして表示される視覚的およびアクセシビリティ ビューに投影されます。":::
   <span data-ttu-id="f55ff-119">エンジン モデルに変換されたコンテンツは、視覚的またはアクセス可能なプレゼンテーションとして表示される視覚的およびアクセシビリティ ビューに投影されます。</span><span class="sxs-lookup"><span data-stu-id="f55ff-119">Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation</span></span>  
:::image-end:::  

<span data-ttu-id="f55ff-120">このMicrosoft Edgeチームは、W3C や他のブラウザー ベンダーと継続的に取り組み、新しい Web プラットフォーム機能に十分な組み込みのアクセシビリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="f55ff-120">The Microsoft Edge team works with the W3C and other browser vendors on an ongoing basis to ensure that new web platform features have sufficient built-in accessibility.</span></span>  

<span data-ttu-id="f55ff-121">ユーザーがサポートする新しい HTML5 機能の[Microsoft Edge、HTML5Accessibility に移動します][HTML5Accessibility]。</span><span class="sxs-lookup"><span data-stu-id="f55ff-121">For information on which new HTML5 features are accessibly supported by Microsoft Edge, navigate to [HTML5Accessibility][HTML5Accessibility].</span></span>  

## <span data-ttu-id="f55ff-122">リソース</span><span class="sxs-lookup"><span data-stu-id="f55ff-122">Resources</span></span>  

#### <span data-ttu-id="f55ff-123">Microsoft Windows UI オートメーション ブログ</span><span class="sxs-lookup"><span data-stu-id="f55ff-123">Microsoft Windows UI Automation Blog</span></span>  

<span data-ttu-id="f55ff-124">[Microsoft の UI オートメーションWindowsブログでは、][ArchiveBlogsWinuiautomation]オートメーション API に関連するトピックWindows説明します。</span><span class="sxs-lookup"><span data-stu-id="f55ff-124">The [Microsoft Windows UI Automation blog][ArchiveBlogsWinuiautomation] covers topics related to the Windows Automation API.</span></span>  

#### <span data-ttu-id="f55ff-125">Web アクセシビリティ イニシアチブ (WAI)</span><span class="sxs-lookup"><span data-stu-id="f55ff-125">Web Accessibility Initiative (WAI)</span></span>  

<span data-ttu-id="f55ff-126">W3C が提供する Web アクセシビリティ イニシアチブ [(WAI)][W3CWaiHome] は、Web のアクセシビリティの向上に役立つ取り組みです。</span><span class="sxs-lookup"><span data-stu-id="f55ff-126">The [Web Accessibility Initiative (WAI)][W3CWaiHome] provided bt the W3C is an effort to help improve the accessibility of the web.</span></span>  <span data-ttu-id="f55ff-127">このサイトには [、Web][W3CWaiGettingstartedOverview]アクセシビリティの使い始 [め、包含][W3CWaiFundamentals]の設計、チュートリアルとプレゼンテーションなど、 [さまざまなリソースが][W3CWaiTeachAdvocate]提供されています。</span><span class="sxs-lookup"><span data-stu-id="f55ff-127">The site provides a variety of resources for [Getting Started with Web Accessibility][W3CWaiGettingstartedOverview], [Designing for Inclusion][W3CWaiFundamentals], [tutorials and presentations][W3CWaiTeachAdvocate], and more.</span></span>  

<!-- links -->  

[AccessibilityBuild]: ./build/index.md "アクセス可能な Web サイトの|Microsoft Doc"  
[AccessibilityDesign]: ./design.md "アクセス可能な Web サイトの|Microsoft Doc"  
[AccessibilityTest]: ./test.md "アクセシビリティ テスト |Microsoft Docs"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI オートメーション |Microsoft Doc"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI オートメーション ブログ |Microsoft Doc"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 アクセシビリティ"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "アクセシビリティ |W3C"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web アクセシビリティ の概要|Web アクセシビリティ イニシアチブ (WAI) |W3C"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "開始方法: Web サイトをアクセス可能なユーザー設定|Web アクセシビリティ イニシアチブ (WAI) |W3C"  
[W3CWaiHome]: https://w3.org/wai "Web アクセシビリティ イニシアチブ (WAI) |W3C"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "ティーチとアドボケートの概要|Web アクセシビリティ イニシアチブ (WAI) |W3C"  

[WHODisabilities]: https://who.int/topics/disabilities "障が|誰が"  

