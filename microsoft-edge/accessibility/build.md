---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: ベストプラクティスとアクセシビリティの高いリッチインターネットアプリケーション (ARIA) を組み合わせて、アクセシビリティ対応の web サイトを作成する方法について説明します。
title: ビルド |機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセシビリティ対応の web サイト、edge、web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 7a8ff5082132ec3270a6e01af594a5bd9fb35389
ms.sourcegitcommit: 5d3802721036dc7cd90e9e6f7ac90dc3acc24eec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "11191554"
---
# <span data-ttu-id="0c4ce-104">アクセシビリティの高い Web サイトを構築する</span><span class="sxs-lookup"><span data-stu-id="0c4ce-104">Building Accessible Websites</span></span>
<span data-ttu-id="0c4ce-105">Web には、HTML、CSS、JavaScript の組み合わせを使って構築された動的で複雑な web サイト、アプリケーション、ユーザーインターフェイスが埋め込まれています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="0c4ce-106">ただし、アクセシビリティを考慮せずに設計および構築すると、 [支援技術](https://webaim.org/articles/motor/assistive) を利用して web を参照するユーザーは、これらの複雑な web サイトを使用することが困難になります。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span> <span data-ttu-id="0c4ce-107">障碍のあるユーザーが使いやすい web サイトを構築するには、ユーザーインターフェイスに関するセマンティクス情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span> <span data-ttu-id="0c4ce-108">これにより、スクリーンリーダーなどの支援技術によって必要な情報を伝えることができるので、web サイトを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>

<span data-ttu-id="0c4ce-109">Microsoft Edge でサポートされている新しい HTML5 機能 accessibly については、 [HTML5Accessibility](https://html5accessibility.com) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

## <span data-ttu-id="0c4ce-110">アクセシビリティのしくみ</span><span class="sxs-lookup"><span data-stu-id="0c4ce-110">How Accessibility Works</span></span>

<span data-ttu-id="0c4ce-111">支援技術により、コンピューターに通常ない機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-111">Assistive technologies add capabilities that computers don't usually have.</span></span> <span data-ttu-id="0c4ce-112">たとえば、視覚障碍のあるユーザーは、マウスと画面でブラウザーを直接使用するのではなく、スクリーンリーダーなどの支援技術と組み合わせてキーボードを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span> <span data-ttu-id="0c4ce-113">Microsoft プラットフォームと web 上のアプリケーションの場合、支援技術は microsoft [UI オートメーション](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、microsoft Edge のドキュメントオブジェクトモデル (DOM)、またはこれらの組み合わせなどのアプリケーション固有のオブジェクトモデルと連携します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx), an application-specific object model such as the Document Object Model (DOM) in Microsoft Edge, or a combination of these.</span></span>

<span data-ttu-id="0c4ce-114">Web 開発者の場合は、特定の HTML 要素が UI オートメーションオブジェクトに対応しているため、これらの HTML 要素を選択するときに、開発者はこれらの要素に組み込まれているアクセシビリティプロパティとイベントを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span> <span data-ttu-id="0c4ce-115">通常、web サイトを作成しているときに、アプリがアクセスできるように、API が正しく書き込まれている (または適切な要素が指定されている) ことを確認するだけで十分です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to (or that the appropriate element is specified), in order for the application to be accessible.</span></span> <span data-ttu-id="0c4ce-116">詳細については [、「Microsoft Edge で ARIA と UI オートメーション](./build/ARIA-and-UI-Automation.md) を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-116">Check out [ARIA and UI Automation in Microsoft Edge](./build/ARIA-and-UI-Automation.md) for more information.</span></span>  <span data-ttu-id="0c4ce-117">アクセシビリティの高いユニバーサル Windows プラットフォーム (UWP) アプリの詳細については、Windows デベロッパーセンターの [アクセシビリティ](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-117">For information on accessible Universal Windows Platform (UWP) apps, see the [Accessibility](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) topic in the Windows Dev Center.</span></span>

<span data-ttu-id="0c4ce-118">動的コンテンツに関する多くの一般的なアクセシビリティの問題については、適切なコーディングの方法で対処できます。 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) ドキュメントには、よりアクセシビリティの高い動的 web アプリケーションを作成するのに役立つ多くの手法とベストプラクティスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span> <span data-ttu-id="0c4ce-119">ただし、適切にコードが記述されている場合でも、動的コンテンツは必ずしもアクセス可能であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span> <span data-ttu-id="0c4ce-120">アクセシビリティに対応した[リッチインターネットアプリケーション (ARIA)](#aria)は、この問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="0c4ce-121">Web アクセシビリティの詳細については、「web アクセシビリティ[イニシアチブ](https://www.w3.org/WAI/)(wai-aria 使った) による[Web アクセシビリティの概要](https://www.w3.org/WAI/intro/accessibility.php)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative](https://www.w3.org/WAI/) (WAI).</span></span>

## <span data-ttu-id="0c4ce-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="0c4ce-122">ARIA</span></span>
<span data-ttu-id="0c4ce-123">W3C's [Web Accessibility イニシアチブ](https://www.w3.org/WAI/)によるアクセシビリティ性の高い[リッチインターネットアプリケーション](https://www.w3.org/TR/wai-aria/)(ARIA) の仕様は、動的な Web コンテンツとカスタムユーザーインターフェイスをすべてのユーザーがアクセスできるようにする構文として定義されています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-123">The [Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI/) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span> <span data-ttu-id="0c4ce-124">ARIA は、カスタムセマンティクスを伝えるために設計された追加の属性 (ロール、プロパティ、状態) を使って HTML を拡張します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-124">ARIA extends HTML by using additional attributes (roles, properties, and states) that are designed to convey custom semantics.</span></span> <span data-ttu-id="0c4ce-125">これらの属性は、ブラウザーでコントロールの状態と役割をアクセシビリティ API に渡すために使われます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>

### <span data-ttu-id="0c4ce-126">役割、プロパティ、状態</span><span class="sxs-lookup"><span data-stu-id="0c4ce-126">Roles, Properties, and States</span></span>
<span data-ttu-id="0c4ce-127">ARIA ロールは、属性を使用して要素に対して設定され、 [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) 要素に関する支援技術とアクセシビリティ api 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-127">ARIA roles are set on elements using the [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) attribute to give assistive technologies and accessibility APIs information about the element.</span></span> <span data-ttu-id="0c4ce-128">たとえば、次の `<li>` 要素は、 `role="menuitem"` メニュー内の項目であることを示すために割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>

``` html
<li role="menuitem">Home</li>
```

<span data-ttu-id="0c4ce-129">ARIA の状態とプロパティは、ロールの特性の定義を形成するために、オブジェクトに関する特定の情報を提供する aria のプレフィックス付き属性です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span> <span data-ttu-id="0c4ce-130">プロパティは、やなどのオブジェクトの性質にとって重要な属性です [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-130">Properties are attributes that are essential to the nature of an object, like [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) and [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx).</span></span> <span data-ttu-id="0c4ce-131">プロパティの変更は、オブジェクトの意味に影響します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-131">Changing a property affects the meaning of the object.</span></span> <span data-ttu-id="0c4ce-132">次の例では、メニュー項目にプロパティを設定して、ポップアップがあることを示してい `aria-haspopup="true"` `<li>` ます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>

``` html
<li role="menuitem" aria-haspopup="true">Open</li>
```

<span data-ttu-id="0c4ce-133">状態はオブジェクトの性質を変更しませんが、またはなどのオブジェクトに関連付けられたオブジェクトまたはユーザーの操作に関連する情報を表し [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) ます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) or [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx).</span></span> <span data-ttu-id="0c4ce-134">たとえば、次の例に示す状態は、 `aria-checked="false"` チェックボックスがオフになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>

``` html
<div role="checkbox" aria-checked="false">Accept</div>
```

<span data-ttu-id="0c4ce-135">すべての役割、プロパティ、状態の一覧を表示するには、W3C による [役割モデル](https://www.w3.org/TR/wai-aria-1.1/#roles) に移動します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1/#roles) by the W3C to see a full list of roles, properties, and states.</span></span>

<span data-ttu-id="0c4ce-136">ARIA の詳細については、「 [リソース](#resources) 」セクションの「aria」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-136">For more information on ARIA, see the ARIA in the [Resources](#resources) section.</span></span>

## <span data-ttu-id="0c4ce-137">支援技術の互換性のテスト</span><span class="sxs-lookup"><span data-stu-id="0c4ce-137">Assistive Technology Compatibility Testing</span></span>  

<span data-ttu-id="0c4ce-138">作成している web サイトが実際の支援技術で動作していることを確認することは、障碍のあるユーザーに優れたエクスペリエンスを実現するための最良の方法です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-138">Verifying that the website you are building works with real assistive technologies is the best way to ensure a good experience for your users with disabilities.</span></span>  <span data-ttu-id="0c4ce-139">多くの支援技術ではキーボードを使用しているため、web サイトのキーボードアクセシビリティをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-139">Since many assistive technologies make use of the keyboard, testing the keyboard accessibility of your website is a good place to start.</span></span>  <span data-ttu-id="0c4ce-140">[キーボード互換性テスト][W3cPerspectiveVideosKeyboard] は、ユーザーがマウスを必要とせずに、すべての対話型コントロールにアクセスできることを検証します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-140">[Keyboard compatibility testing][W3cPerspectiveVideosKeyboard] validates that users have access to all interactive controls without requiring a mouse.</span></span>  <span data-ttu-id="0c4ce-141">Microsoft [Accessibility Insights For Web][AccessibilityinsightsWebOverview] は microsoft Edge と Chrome 用のブラウザー拡張であり、このガイドを使用すると、いくつかの一般的な問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] is a browser extension for Microsoft Edge and Chrome that guides you and reveals several common issues.</span></span>  

<span data-ttu-id="0c4ce-142">Web サイトがキーボードで適切に動作することを確認したら、スクリーンリーダーなどの他の支援技術を使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-142">Once you are confident that your website works well with a keyboard, try it with other assistive technologies, such as screen readers.</span></span>  <span data-ttu-id="0c4ce-143">次の問題が明らかになります。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-143">It uncover issues in the following.</span></span>

*   <span data-ttu-id="0c4ce-144">HTML、ARIA、CSS。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-144">Your HTML, ARIA, and CSS.</span></span>  
*   <span data-ttu-id="0c4ce-145">機能または技術の支援技術のサポートレベル。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-145">The level of support of an assistive technology for a feature or technique.</span></span>  
    
<span data-ttu-id="0c4ce-146">各ブラウザーでは、プラットフォームのアクセシビリティ Api と Microsoft Edge で異なる要素を対応付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-146">Different browsers may map elements to platform accessibility APIs differently than Microsoft Edge.</span></span>  <span data-ttu-id="0c4ce-147">インターフェイスの構築中に、それぞれの違いを考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-147">While building your interface, it is important to consider each difference.</span></span>  

<span data-ttu-id="0c4ce-148">[Web ターゲット] は、 [スクリーンリーダー][WebaimProjectsScreenreadersurvey8] と [視覚に障碍][WebaimProjectsLowvisionsurvey2] のあるユーザーを対象に調査を実施し、テストする支援技術とブラウザーを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-148">WebAIM conducts surveys with [screen reader][WebaimProjectsScreenreadersurvey8] and [low vision][WebaimProjectsLowvisionsurvey2] users that help you decide which assistive technologies and browsers you want to test.</span></span>  

### <span data-ttu-id="0c4ce-149">テスト方法を学ぶ</span><span class="sxs-lookup"><span data-stu-id="0c4ce-149">Learning How to Test</span></span>  

<span data-ttu-id="0c4ce-150">支援技術は、洗練されたツールです。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-150">Assistive technologies are sophisticated tools.</span></span>  <span data-ttu-id="0c4ce-151">この機能について最初に学習しなくても、支援技術を使用してすぐにテストを開始できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-151">Do not assume that you are able to immediately start testing with an assistive technology without first learning about how it works.</span></span>  <span data-ttu-id="0c4ce-152">スクリーンリーダーを使用してテストする方法には、特に急な学習曲線が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-152">Learning to test with a screen reader has an especially steep learning curve.</span></span>  <span data-ttu-id="0c4ce-153">初心者のスクリーンリーダーユーザーは、スクリーンリーダーの誤用に関連して、スクリーンリーダーのバグが発生したと想定している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-153">A novice screen reader user may assume that a screen reader bug has occurred while the issue is related to misuse of the screen reader.</span></span>  

<span data-ttu-id="0c4ce-154">支援技術を使用してテストする方法の詳細については、「WebAIM の [スクリーンリーダーを使用したテスト][WebaimArticlesScreenreaderTesting] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-154">For more information about learning to test with assistive technologies, navigate to [Testing with Screen Readers][WebaimArticlesScreenreaderTesting] on WebAIM.</span></span>  

### <span data-ttu-id="0c4ce-155">ローカルでのテスト</span><span class="sxs-lookup"><span data-stu-id="0c4ce-155">Testing Locally</span></span>  

<span data-ttu-id="0c4ce-156">ほとんどのデバイスには、OS に組み込まれている支援技術が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-156">Most devices include assistive technology that is built-in to the OS.</span></span>  <span data-ttu-id="0c4ce-157">Microsoft Windows には、 [Windows ナレーター][MicrosoftSupport22798] のスクリーンリーダーと [windows 拡大鏡][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-157">Microsoft Windows includes the [Windows Narrator][MicrosoftSupport22798] screen reader and [Windows Magnifier][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198].</span></span>  <span data-ttu-id="0c4ce-158">[Nvda][NvaccessAboutNvda]、 [FreedomscientificSoftwareJaws]、 [ZoomText][FreedomscientificSoftwareZoomtext]などのサードパーティの支援技術をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-158">3rd party assistive technologies like [NVDA][NvaccessAboutNvda], [FreedomscientificSoftwareJaws], and [ZoomText][FreedomscientificSoftwareZoomtext] are available to download.</span></span>  <span data-ttu-id="0c4ce-159">Apple macOS には、 [VoiceOver][AppleAccessibilityMacVision] スクリーンリーダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-159">Apple macOS includes the [VoiceOver][AppleAccessibilityMacVision] screen reader.</span></span>  <span data-ttu-id="0c4ce-160">IOS、Android、Linux はすべて、さまざまな支援技術をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-160">And iOS, Android, and Linux all support a variety of assistive technologies.</span></span>  

### <span data-ttu-id="0c4ce-161">仮想マシンとエミュレーターでのテスト</span><span class="sxs-lookup"><span data-stu-id="0c4ce-161">Testing in Virtual Machines and Emulators</span></span>  

<span data-ttu-id="0c4ce-162">MacOS では、windows ナレーターや NVDA など、Windows でのみ利用可能な支援技術を使ってテストする場合は、Windows 仮想マシンを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-162">Under macOS, if you want to test with an assistive technology only available for Windows, like Windows Narrator or NVDA, create a Windows virtual machine.</span></span>  <span data-ttu-id="0c4ce-163">Microsoft Edge \ (EdgeHTML \) と IE の仮想マシンは、 [仮想マシンのダウンロードページ][MicrosoftDeveloperEdgeVms]で、Virtualbox および VMWare で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-163">Virtual machines with Microsoft Edge \(EdgeHTML\) and IE are available for VirtualBox and VMWare on the [Virtual Machines download page][MicrosoftDeveloperEdgeVms].</span></span>  

<span data-ttu-id="0c4ce-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] には、 [Android のアクセシビリティスイート][GooglePlayStoreAndroidAccessibilitySuite]で支援技術をテストするためのエミュレーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] includes an emulator that for you to test assistive technologies in the [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite].</span></span>  <span data-ttu-id="0c4ce-165">指示に従って [仮想デバイス][AndroidDeveloperDevicesManagingAvdsHtml] をセットアップし、 [エミュレーターを起動][AndroidDeveloperDevicesEmulatorHtml]してから、GooglePlay Store から [Android アクセシビリティスイート][GooglePlayStoreAndroidAccessibilitySuite] をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-165">Follow the instructions to [set up a virtual device][AndroidDeveloperDevicesManagingAvdsHtml] and [start the emulator][AndroidDeveloperDevicesEmulatorHtml], then install [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite] from the GooglePlay store.</span></span>  

> [!NOTE]
> <span data-ttu-id="0c4ce-166">IOS シミュレータには現在、VoiceOver が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-166">The iOS Simulator does not currently include VoiceOver.</span></span>  

### <span data-ttu-id="0c4ce-167">クラウドベースのテストツール</span><span class="sxs-lookup"><span data-stu-id="0c4ce-167">Cloud-based Testing Tools</span></span>  

<span data-ttu-id="0c4ce-168">OS で支援技術が利用できない場合、または仮想マシンまたはエミュレーターに支援技術をインストールできない場合は、クラウドベースの支援技術テストツールが次のベストレベルになります。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-168">If an assistive technology is not available on your OS or you not possible to install one on a virtual machine or emulator, cloud-based assistive technology testing tools are the next best thing.</span></span>  

*   <span data-ttu-id="0c4ce-169">Office では、最新の web ブラウザーを使用して、支援技術を使用して手動でテスト[することが][AssistivlabsMain]できます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-169">[Assistiv Labs (commercial)][AssistivlabsMain] enables you to manually test with assistive technologies through any modern web browser.</span></span>  <span data-ttu-id="0c4ce-170">支援技術とブラウザーを選択すると、対話式の仮想マシン、エミュレーター、または実際のデバイスに接続されます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-170">Choose an assistive technology and browser and it connects you with a virtual machine, emulator, or real device with which you may interact.</span></span>  

## <span data-ttu-id="0c4ce-171">リソース</span><span class="sxs-lookup"><span data-stu-id="0c4ce-171">Resources</span></span>

### <span data-ttu-id="0c4ce-172">アクセシビリティの基本</span><span class="sxs-lookup"><span data-stu-id="0c4ce-172">Accessibility Basics</span></span>
#### [<span data-ttu-id="0c4ce-173">A11Y プロジェクト</span><span class="sxs-lookup"><span data-stu-id="0c4ce-173">The A11Y Project</span></span>](http://a11yproject.com/)
<span data-ttu-id="0c4ce-174">A11Y プロジェクトは、web アクセシビリティを容易にするための、コミュニティ主導の作業です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-174">The A11Y Project is a community-driven effort to make web accessibility easier.</span></span> <span data-ttu-id="0c4ce-175">[A11Y プロジェクト](https://a11yproject.com/)サイトでは、基本的なアクセシビリティの原則、アクセシビリティ対応のパターンとウィジェット[ライブラリ](https://a11yproject.com/patterns)、アクセシビリティソフトウェア、ブログ、書籍、ツールに関する[リソース](http://a11yproject.com/resources.html)について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-175">Check out [The A11Y Project](https://a11yproject.com/) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>

#### [<span data-ttu-id="0c4ce-176">Web アクセシビリティイニシアチブ (WAI-ARIA 使った)</span><span class="sxs-lookup"><span data-stu-id="0c4ce-176">Web Accessibility Initiative (WAI)</span></span>](https://w3.org/WAI/)
<span data-ttu-id="0c4ce-177">W3C's Web Accessibility イニシアチブ (WAI-ARIA 使った) は、web のアクセシビリティを向上させるための取り組みです。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-177">The W3C's Web Accessibility Initiative (WAI) is an effort to help improve the accessibility of the web.</span></span> <span data-ttu-id="0c4ce-178">[Web アクセシビリティの使用を開始](https://www.w3.org/WAI/gettingstarted/Overview.html)するためのさまざまなリソースが用意されており、それを対象とした[デザイン](https://www.w3.org/WAI/users/Overview.html)、[チュートリアル、プレゼンテーション](https://www.w3.org/WAI/train.html)などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-178">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>

### <span data-ttu-id="0c4ce-179">アクセシビリティのブログ</span><span class="sxs-lookup"><span data-stu-id="0c4ce-179">Accessibility Blogs</span></span>
#### [<span data-ttu-id="0c4ce-180">Paciello グループ</span><span class="sxs-lookup"><span data-stu-id="0c4ce-180">The Paciello Group</span></span>](https://www.paciellogroup.com/blog/)
<span data-ttu-id="0c4ce-181">Paciello グループは、世界中の組織に対してコンサルティングと技術のソリューションを提供します。顧客がすべての対象ユーザーに対して効率的かつ効率的に連絡を取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-181">The Paciello Group provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span> <span data-ttu-id="0c4ce-182">Web アクセシビリティのベストプラクティス、アクセシビリティツール、アクセシビリティの傾向などのトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-182">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>

#### [<span data-ttu-id="0c4ce-183">簡単にアクセス</span><span class="sxs-lookup"><span data-stu-id="0c4ce-183">Simply Accessible</span></span>](http://simplyaccessible.com/articles/)
<span data-ttu-id="0c4ce-184">アクセシビリティのトレーニング、コンサルティングなど、web 上のアクセシビリティの認識を向上させるアクセシビリティスペシャリストのチームであるということができます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-184">Simply Accessible is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span> <span data-ttu-id="0c4ce-185">この [セクションでは、web](http://simplyaccessible.com/articles/) アクセシビリティ、アクセシビリティの高いデザインに関するベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-185">Their [Articles](http://simplyaccessible.com/articles/) section discusses best practices for web accessibility, accessible design, and more.</span></span>

#### [<span data-ttu-id="0c4ce-186">SSB BART グループ (SSB)</span><span class="sxs-lookup"><span data-stu-id="0c4ce-186">SSB BART Group (SSB)</span></span>](http://www.ssbbartgroup.com/blog/)
<span data-ttu-id="0c4ce-187">SSB BART グループは、アクセシビリティ対応の製品とサービスの開発と展開において、クライアントをサポートするデジタルアクセシビリティ企業です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-187">SSB BART Group is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span> <span data-ttu-id="0c4ce-188">これらのブログは、ARIA のベストプラクティス、アクセシビリティの傾向、ウェビナーなどのトピックに対応しています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-188">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>

### <span data-ttu-id="0c4ce-189">アクセシビリティの高い例</span><span class="sxs-lookup"><span data-stu-id="0c4ce-189">Accessible Examples</span></span>
#### [<span data-ttu-id="0c4ce-190">ally.js-チュートリアル</span><span class="sxs-lookup"><span data-stu-id="0c4ce-190">ally.js - Tutorials</span></span>](http://allyjs.io/tutorials/)
<span data-ttu-id="0c4ce-191">アクセシビリティをより簡単にするために、アクセシビリティに関する問題を解決するための JavaScript ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-191">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>

#### [<span data-ttu-id="0c4ce-192">Heydonworks-ARIA の例</span><span class="sxs-lookup"><span data-stu-id="0c4ce-192">Heydonworks - ARIA Examples</span></span>](http://heydonworks.com/practical_aria_examples/)
<span data-ttu-id="0c4ce-193">アプリケーションのアクセシビリティを向上させるための実用的な ARIA の例</span><span class="sxs-lookup"><span data-stu-id="0c4ce-193">Practical ARIA examples to enhance your application accessibility</span></span>

#### [<span data-ttu-id="0c4ce-194">OpenAjax の例</span><span class="sxs-lookup"><span data-stu-id="0c4ce-194">OpenAjax Examples</span></span>](http://oaa-accessibility.org/)
<span data-ttu-id="0c4ce-195">OpenAjax アライアンス web サイトは、WAI-ARIA 使ったの規則を確認するための優れたリソースであり、WAI-ARIA 使ったのいくつかの実装の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-195">The OpenAjax Alliance website is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>

#### [<span data-ttu-id="0c4ce-196">傾向</span><span class="sxs-lookup"><span data-stu-id="0c4ce-196">Patterns</span></span>](http://a11yproject.com/patterns.html)
<span data-ttu-id="0c4ce-197">[A11Y プロジェクトに](http://a11yproject.com/) は、メニュー、ボタン、ヒントなど、アクセシビリティ対応のウィジェットとパターンのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-197">[The A11Y Project](http://a11yproject.com/) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>

### <span data-ttu-id="0c4ce-198">ユーザー補助の手法 & ツール</span><span class="sxs-lookup"><span data-stu-id="0c4ce-198">Accessibility Techniques & Tools</span></span>
#### [<span data-ttu-id="0c4ce-199">アクセシビリティ: Microsoft Edge のアクセシビリティ対応の拡張機能を作成する</span><span class="sxs-lookup"><span data-stu-id="0c4ce-199">Accessibility: Creating accessible extension icons for Microsoft Edge</span></span>](../extensions/guides/accessibility.md)
<span data-ttu-id="0c4ce-200">Microsoft Edge のアクセシビリティ対応の拡張機能の作成に関するガイダンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-200">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>

#### [<span data-ttu-id="0c4ce-201">アクセシビリティ対応の名前と説明: 計算とマッピング1.1</span><span class="sxs-lookup"><span data-stu-id="0c4ce-201">Accessible Name and Description: Computation and Mappings 1.1</span></span>](https://www.w3.org/TR/accname-1.1/)
<span data-ttu-id="0c4ce-202">この W3C マッピングドキュメントでは、ブラウザーが web コンテンツ言語からアクセシビリティの高いオブジェクトの名前と説明を特定し、アクセシビリティ Api でそれらを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-202">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>

#### [<span data-ttu-id="0c4ce-203">アクセシビリティ評価リソース</span><span class="sxs-lookup"><span data-stu-id="0c4ce-203">Accessibility Evaluation Resources</span></span>](https://www.w3.org/WAI/eval/Overview.html)
<span data-ttu-id="0c4ce-204">アクセシビリティ評価リソースは、アクセシビリティのために web サイトを評価するためのさまざまな方法を示す W3C のマルチページリソースです。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-204">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>

#### [<span data-ttu-id="0c4ce-205">支援技術の互換性テスト</span><span class="sxs-lookup"><span data-stu-id="0c4ce-205">Assistive technology compatibility tests</span></span>](http://www.powermapper.com/tests/)
<span data-ttu-id="0c4ce-206">スクリーンリーダーのように、さまざまなコンテンツの種類や標準が支援技術 (AT) でどのように動作するかを示すテスト結果。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-206">Test results showing how different content types and standards behave in assistive technologies (AT) like screen readers.</span></span>

#### [<span data-ttu-id="0c4ce-207">アクセシビリティの高い web サイトを作成するのがとても簡単に</span><span class="sxs-lookup"><span data-stu-id="0c4ce-207">Building accessible websites just got a lot easier</span></span>](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)
<span data-ttu-id="0c4ce-208">この .NET Web 開発とツールのブログ投稿では、Visual Studio 拡張機能の [Web アクセシビリティチェック](https://go.microsoft.com/fwlink/p/?linkid=841539)について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-208">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://go.microsoft.com/fwlink/p/?linkid=841539).</span></span>

#### [<span data-ttu-id="0c4ce-209">Core Accessibility API マッピング1.1</span><span class="sxs-lookup"><span data-stu-id="0c4ce-209">Core Accessibility API Mappings 1.1</span></span>](https://www.w3.org/TR/core-aam-1.1/)
<span data-ttu-id="0c4ce-210">この W3C マッピングドキュメントでは、web コンテンツ言語がアクセシビリティ Api にどのように公開されるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-210">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  

#### [<span data-ttu-id="0c4ce-211">簡単なチェック– Web アクセシビリティの最初のレビュー</span><span class="sxs-lookup"><span data-stu-id="0c4ce-211">Easy Checks – A First Review of Web Accessibility</span></span>](https://www.w3.org/WAI/eval/preliminary.html)
<span data-ttu-id="0c4ce-212">WAI-ARIA 使ったによって、web ページのアクセシビリティを向上させるための一連のクイックチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-212">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>

#### [<span data-ttu-id="0c4ce-213">WCAG 2.0 の対応方法</span><span class="sxs-lookup"><span data-stu-id="0c4ce-213">How to Meet WCAG 2.0</span></span>](https://www.w3.org/WAI/WCAG20/quickref/)
<span data-ttu-id="0c4ce-214">Web コンテンツのアクセシビリティガイドライン (WCAG) 2.0 の要件 (成功の条件) と手法のクイックリファレンス。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-214">A quick reference to Web Content Accessibility Guidelines (WCAG) 2.0 requirements (success criteria) and techniques.</span></span>

#### [<span data-ttu-id="0c4ce-215">HTML アクセシビリティ API マッピング1.0</span><span class="sxs-lookup"><span data-stu-id="0c4ce-215">HTML Accessibility API Mappings 1.0</span></span>](https://www.w3.org/TR/html-aam-1.0/)
<span data-ttu-id="0c4ce-216">この W3C マッピングドキュメントでは、HTML 5.1 の要素と属性が platform accessibility Api にどのように対応するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-216">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>


#### [<span data-ttu-id="0c4ce-217">ポップヒント</span><span class="sxs-lookup"><span data-stu-id="0c4ce-217">Quick Tips</span></span>](http://a11yproject.com/#Quick-tips)
<span data-ttu-id="0c4ce-218">[A11Y プロジェクト](http://a11yproject.com/)でのアクセシビリティに関する web 開発のクイックヒントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-218">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com/).</span></span>

#### [<span data-ttu-id="0c4ce-219">サイトのスキャン</span><span class="sxs-lookup"><span data-stu-id="0c4ce-219">Site Scan</span></span>](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)
<span data-ttu-id="0c4ce-220">Microsoft Edge デベロッパーセンターのサイトスキャンツールは、古いライブラリ、レイアウトの問題、アクセシビリティの問題をチェックします。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-220">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>

#### [<span data-ttu-id="0c4ce-221">WCAG 2.0 の手法</span><span class="sxs-lookup"><span data-stu-id="0c4ce-221">Techniques for WCAG 2.0</span></span>](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)
<span data-ttu-id="0c4ce-222">会議 [Web コンテンツのアクセシビリティガイドライン (WCAG) 2.0](https://w3.org/TR/WCAG20/) の成功条件について web 開発者向けのガイダンスを提供する W3C の手法。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-222">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20/) success criteria.</span></span>

#### [<span data-ttu-id="0c4ce-223">Web アクセシビリティの開発に関するヒント</span><span class="sxs-lookup"><span data-stu-id="0c4ce-223">Tips on Developing for Web Accessibility</span></span>](https://w3.org/WAI/gettingstarted/tips/developing.html)
<span data-ttu-id="0c4ce-224">障碍のある方にとって使いやすい web コンテンツの開発に関する W3C のヒント。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-224">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>

#### [<span data-ttu-id="0c4ce-225">WAI-ARIA 使った-ARIA のオーサリングプラクティス1.1</span><span class="sxs-lookup"><span data-stu-id="0c4ce-225">WAI-ARIA Authoring Practices 1.1</span></span>](http://w3c.github.io/aria-practices/)
<span data-ttu-id="0c4ce-226">WAI-ARIA 使った-ARIA 1.1 の使用方法を理解し、WAI-ARIA 使った-ARIA の役割、状態、プロパティを使ってアクセスできるウィジェット、ナビゲーション、動作を実現するためのアプローチを提供する、W3C によるドキュメント。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-226">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>

#### [<span data-ttu-id="0c4ce-227">WAI-ARIA 使ったのガイドラインと手法</span><span class="sxs-lookup"><span data-stu-id="0c4ce-227">WAI Guidelines and Techniques</span></span>](https://w3.org/WAI/guid-tech.html)
<span data-ttu-id="0c4ce-228">WAI-ARIA 使ったによって開発された一連の web アクセシビリティガイドラインと標準。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-228">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  

#### [<span data-ttu-id="0c4ce-229">Web アクセシビリティ評価ツールの一覧</span><span class="sxs-lookup"><span data-stu-id="0c4ce-229">Web Accessibility Evaluation Tools List</span></span>](https://www.w3.org/WAI/ER/tools/index.html)
<span data-ttu-id="0c4ce-230">Web サイトがアクセシビリティガイドラインを満たしているかどうかを判断するのに役立つ web アクセシビリティ評価ツールの一覧です。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-230">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>

#### [<span data-ttu-id="0c4ce-231">Web アクセシビリティの観点: すべてのユーザーに対する影響と利点を調べる</span><span class="sxs-lookup"><span data-stu-id="0c4ce-231">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>](https://w3.org/WAI/perspectives/)
<span data-ttu-id="0c4ce-232">アクセシビリティの影響とすべてのユーザーの利点について、W3C による一連の短いビデオ。</span><span class="sxs-lookup"><span data-stu-id="0c4ce-232">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "仮想マシン |Microsoft Edge 開発者"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 "ナレーターの詳細なガイド |Microsoft サポート"  
[MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]: https://support.microsoft.com/windows/414948ba-8b1c-d3bd-8615-0e5e32204198 "拡大鏡を使って画面上の項目を簡単に表示する |Microsoft サポート"  

[AccessibilityinsightsWebOverview]: https://accessibilityinsights.io/docs/web/overview "Web 用のアクセシビリティ分析 |アクセシビリティの分析"  

[AndroidDeveloperDevicesManagingAvdsHtml]: https://developer.android.com/tools/devices/managing-avds.html "仮想デバイスを作成して管理するAndroid 開発者"  
[AndroidDeveloperDevicesEmulatorHtml]: https://developer.android.com/tools/devices/emulator.html "Android エミュレーターでアプリを実行する |Android 開発者"  
[AndroidDeveloperSdkInstallingStudioHtml]: https://developer.android.com/sdk/installing/studio.html "Android Studio をダウンロード |Android 開発者"  

[AppleAccessibilityMacVision]: https://www.apple.com/accessibility/mac/vision "視覚補助機能-Mac |アップル"  

[AssistivlabsMain]: https://assistivlabs.com "アシスタント"  

[FreedomscientificSoftwareJaws]: https://www.freedomscientific.com/products/software/jaws "JAWS® |自由関数"  
[FreedomscientificSoftwareZoomtext]: https://www.freedomscientific.com/products/software/zoomtext "ZoomText |自由関数"  

[GooglePlayStoreAndroidAccessibilitySuite]: https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback "Android アクセシビリティスイート |GooglePlay ストア"  

[NvaccessAboutNvda]: https://www.nvaccess.org/about-nvda "NVDA について |NV アクセス"  

[W3cPerspectiveVideosKeyboard]: https://www.w3.org/WAI/perspective-videos/keyboard "キーボードの互換性 |勧告"  

[WebaimProjectsLowvisionsurvey2]: https://webaim.org/projects/lowvisionsurvey2 "視覚障碍のあるユーザーの調査 \ #2 の結果 |WebAIM"  
[WebaimProjectsScreenreadersurvey8]: https://webaim.org/projects/screenreadersurvey8 "スクリーンリーダーのユーザーアンケート \ #8 の結果 |WebAIM"  
[WebaimArticlesScreenreaderTesting]: https://webaim.org/articles/screenreader_testing "スクリーンリーダーを使用したテスト |WebAIM"  
