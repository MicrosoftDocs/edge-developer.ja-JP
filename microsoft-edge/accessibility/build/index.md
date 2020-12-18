---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: ベスト プラクティスと Accessible Rich Internet Applications (ARIA) を組み合わせて、アクセス可能な Web サイトを作成する方法について説明します。
title: ビルド |アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ, 開発者向けアクセシビリティ, アクセシビリティ対応の Web サイト, エッジ, Web 開発, ARIA, 開発者, UIA, UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 40ab1acd0b5356ad4696cde0762f656708a67890
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234503"
---
# <span data-ttu-id="c68f6-104">アクセス可能な Web サイトの構築</span><span class="sxs-lookup"><span data-stu-id="c68f6-104">Building Accessible Websites</span></span>

<span data-ttu-id="c68f6-105">Web には、HTML、CSS、JavaScript の組み合わせを使用して構築された、動的で複雑な Web サイト、アプリケーション、およびユーザー インターフェイスが埋め込みされています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="c68f6-106">ただし、アクセシビリティを考慮せずに設計および構築した場合、これらの複雑な Web サイトは、支援技術を利用[](https://webaim.org/articles/motor/assistive)して Web を閲覧するユーザーが使用することは困難です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span> <span data-ttu-id="c68f6-107">障がいのあるユーザーがアクセスできる Web サイトを構築するには、ユーザー インターフェイスに関するセマンティック情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span> <span data-ttu-id="c68f6-108">これにより、スクリーン リーダーなどの支援技術は、さまざまな機能を持つユーザーが Web サイトを使用するのに役立つ必要な情報を伝えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>

<span data-ttu-id="c68f6-109">Microsoft Edge でサポートされている新しい HTML5 機能に関する情報については [、HTML5Accessibility](https://html5accessibility.com) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

## <span data-ttu-id="c68f6-110">アクセシビリティのしくみ</span><span class="sxs-lookup"><span data-stu-id="c68f6-110">How Accessibility Works</span></span>

<span data-ttu-id="c68f6-111">支援技術によって、コンピューターには通常はない機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-111">Assistive technologies add capabilities that computers don't usually have.</span></span> <span data-ttu-id="c68f6-112">たとえば、視覚障がいのあるユーザーは、ブラウザーをマウスや画面で直接使うのではなく、スクリーン リーダーなどの支援技術と組み合わせてキーボードを使う場合があります。</span><span class="sxs-lookup"><span data-stu-id="c68f6-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span> <span data-ttu-id="c68f6-113">Microsoft プラットフォーム上および Web 上のアプリケーションの場合、支援技術は Microsoft [UI オートメーション](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、Microsoft Edge のドキュメント オブジェクト モデル (DOM) などのアプリケーション固有のオブジェクト モデル、またはこれらを組み合わせて操作します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx), an application-specific object model such as the Document Object Model (DOM) in Microsoft Edge, or a combination of these.</span></span>

<span data-ttu-id="c68f6-114">Web 開発者の場合、特定の HTML 要素は UI オートメーション オブジェクトにマップされます。そのため、これらの HTML 要素を選択する場合、開発者はそれらの要素に組み込みのアクセシビリティ プロパティとイベントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span> <span data-ttu-id="c68f6-115">Web サイトを開発する場合、アプリケーションにアクセスするには、通常、API が正しく書き込まれる (または適切な要素が指定されている) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68f6-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to (or that the appropriate element is specified), in order for the application to be accessible.</span></span> <span data-ttu-id="c68f6-116">詳細については [、Microsoft Edge で ARIA と UI](./ARIA-and-UI-Automation.md) オートメーションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-116">Check out [ARIA and UI Automation in Microsoft Edge](./ARIA-and-UI-Automation.md) for more information.</span></span>  <span data-ttu-id="c68f6-117">アクセシビリティ対応のユニバーサル Windows プラットフォーム (UWP) アプリについて[](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)詳しくは、Windows デベロッパー センターのアクセシビリティに関するトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-117">For information on accessible Universal Windows Platform (UWP) apps, see the [Accessibility](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) topic in the Windows Dev Center.</span></span>

<span data-ttu-id="c68f6-118">動的コンテンツに関する一般的なアクセシビリティの問題の多くは、適切なコーディング手法によって解決できます [。WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) のドキュメントには、よりアクセシビリティの高い動的 Web アプリケーションを作成するのに役立つ多くの手法とベスト プラクティスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span> <span data-ttu-id="c68f6-119">ただし、適切にコード化されている場合でも、動的コンテンツにアクセスできるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="c68f6-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span> <span data-ttu-id="c68f6-120">[アクセス可能なリッチ インターネット アプリケーション (ARIA) は、この問題](#aria) を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="c68f6-121">Web アクセシビリティの詳細については [、「Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) Initiative (INITIATIVE) による [Web アクセシビリティの](https://www.w3.org/WAI/) 概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative](https://www.w3.org/WAI/) (WAI).</span></span>

## <span data-ttu-id="c68f6-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="c68f6-122">ARIA</span></span>

<span data-ttu-id="c68f6-123">W3C の[Web アクセシビリティ](https://www.w3.org/WAI/)イニシアチブによる[Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) の仕様は、動的な Web コンテンツとカスタム ユーザー インターフェイスをすべてのユーザーがアクセス可能にするための構文として定義されています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-123">The [Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI/) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span> <span data-ttu-id="c68f6-124">ARIA は、カスタム セマンティクスを伝達するように設計された追加の属性 (ロール、プロパティ、状態) を使用して HTML を拡張します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-124">ARIA extends HTML by using additional attributes (roles, properties, and states) that are designed to convey custom semantics.</span></span> <span data-ttu-id="c68f6-125">これらの属性は、ブラウザーがコントロールの状態とロールをアクセシビリティ API に渡すのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>

### <span data-ttu-id="c68f6-126">ロール、プロパティ、および状態</span><span class="sxs-lookup"><span data-stu-id="c68f6-126">Roles, Properties, and States</span></span>

<span data-ttu-id="c68f6-127">ARIA ロールは、この属性を使って要素に対して設定され、要素に関する支援技術とアクセシビリティ [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) API 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-127">ARIA roles are set on elements using the [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) attribute to give assistive technologies and accessibility APIs information about the element.</span></span> <span data-ttu-id="c68f6-128">たとえば、メニュー内の項目を示す次の要素が `<li>` `role="menuitem"` 割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>

```html
<li role="menuitem">Home</li>
```

<span data-ttu-id="c68f6-129">ARIA の状態とプロパティは、オブジェクトに関する特定の情報を提供する aria-prefixed 属性であり、ロールの性質の定義を形成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span> <span data-ttu-id="c68f6-130">プロパティは、オブジェクトの性質に不可欠な属性です。次に例を示 [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) します [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="c68f6-130">Properties are attributes that are essential to the nature of an object, like [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) and [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx).</span></span> <span data-ttu-id="c68f6-131">プロパティを変更すると、オブジェクトの意味に影響します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-131">Changing a property affects the meaning of the object.</span></span> <span data-ttu-id="c68f6-132">次の例では、このプロパティがポップアップを持つメニュー項目 `aria-haspopup="true"` `<li>` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>

```html
<li role="menuitem" aria-haspopup="true">Open</li>
```

<span data-ttu-id="c68f6-133">状態は、オブジェクトの性質を変更しませんが、オブジェクトまたはオブジェクトとのユーザーの操作に関連付けられている情報を表します。次に示す操作を行 [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) います [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="c68f6-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) or [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx).</span></span> <span data-ttu-id="c68f6-134">たとえば、次の `aria-checked="false"` 例の状態は、チェック ボックスがオフになっていることを表しています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>

```html
<div role="checkbox" aria-checked="false">Accept</div>
```

<span data-ttu-id="c68f6-135">W3C [によるロール モデル](https://www.w3.org/TR/wai-aria-1.1/#roles) に移動して、ロール、プロパティ、および状態の完全な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1/#roles) by the W3C to see a full list of roles, properties, and states.</span></span>

<span data-ttu-id="c68f6-136">ARIA の詳細については、「リソース」セクションの「ARIA」を [参照](#resources) してください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-136">For more information on ARIA, see the ARIA in the [Resources](#resources) section.</span></span>

## <span data-ttu-id="c68f6-137">支援技術の互換性テスト</span><span class="sxs-lookup"><span data-stu-id="c68f6-137">Assistive Technology Compatibility Testing</span></span>  

<span data-ttu-id="c68f6-138">構築する Web サイトが実際の支援技術で動作することの確認は、障がいのあるユーザーに適切なエクスペリエンスを提供する最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-138">Verifying that the website you are building works with real assistive technologies is the best way to ensure a good experience for your users with disabilities.</span></span>  <span data-ttu-id="c68f6-139">多くの支援技術ではキーボードを利用しています。Web サイトのキーボード アクセシビリティのテストは、最初に行うのに良い場所です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-139">Since many assistive technologies make use of the keyboard, testing the keyboard accessibility of your website is a good place to start.</span></span>  <span data-ttu-id="c68f6-140">[キーボード互換性テストでは][W3cPerspectiveVideosKeyboard] 、マウスを使わずにすべての対話型コントロールにアクセスできるユーザーを検証します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-140">[Keyboard compatibility testing][W3cPerspectiveVideosKeyboard] validates that users have access to all interactive controls without requiring a mouse.</span></span>  <span data-ttu-id="c68f6-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] は、Microsoft Edge と Chrome のブラウザー拡張機能であり、いくつかの一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] is a browser extension for Microsoft Edge and Chrome that guides you and reveals several common issues.</span></span>  

<span data-ttu-id="c68f6-142">キーボードで Web サイトが正常に動作すると確信したら、スクリーン リーダーなどの他の支援技術で試してみてください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-142">Once you are confident that your website works well with a keyboard, try it with other assistive technologies, such as screen readers.</span></span>  <span data-ttu-id="c68f6-143">次の問題を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="c68f6-143">It uncover issues in the following.</span></span>

*   <span data-ttu-id="c68f6-144">HTML、ARIA、および CSS。</span><span class="sxs-lookup"><span data-stu-id="c68f6-144">Your HTML, ARIA, and CSS.</span></span>  
*   <span data-ttu-id="c68f6-145">機能または技術に対する支援技術のサポート レベル。</span><span class="sxs-lookup"><span data-stu-id="c68f6-145">The level of support of an assistive technology for a feature or technique.</span></span>  
    
<span data-ttu-id="c68f6-146">ブラウザーによって、Microsoft Edge とは異なる方法で要素がプラットフォーム アクセシビリティ API にマップされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c68f6-146">Different browsers may map elements to platform accessibility APIs differently than Microsoft Edge.</span></span>  <span data-ttu-id="c68f6-147">インターフェイスを構築する際には、それぞれの違いを考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-147">While building your interface, it is important to consider each difference.</span></span>  

<span data-ttu-id="c68f6-148">WebAIM では、スクリーン[][WebaimProjectsScreenreadersurvey8]リーダーと[][WebaimProjectsLowvisionsurvey2]低ビジョン ユーザーを使用してアンケートを実施し、テストする支援技術とブラウザーを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-148">WebAIM conducts surveys with [screen reader][WebaimProjectsScreenreadersurvey8] and [low vision][WebaimProjectsLowvisionsurvey2] users that help you decide which assistive technologies and browsers you want to test.</span></span>  

### <span data-ttu-id="c68f6-149">テスト方法の学習</span><span class="sxs-lookup"><span data-stu-id="c68f6-149">Learning How to Test</span></span>  

<span data-ttu-id="c68f6-150">支援技術は高度なツールです。</span><span class="sxs-lookup"><span data-stu-id="c68f6-150">Assistive technologies are sophisticated tools.</span></span>  <span data-ttu-id="c68f6-151">支援技術を使用してすぐにテストを開始できると想定し、その動作について最初に知らなくても行ってください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-151">Do not assume that you are able to immediately start testing with an assistive technology without first learning about how it works.</span></span>  <span data-ttu-id="c68f6-152">スクリーン リーダーを使ったテストの学習には、特に学習曲線があります。</span><span class="sxs-lookup"><span data-stu-id="c68f6-152">Learning to test with a screen reader has an especially steep learning curve.</span></span>  <span data-ttu-id="c68f6-153">スクリーン リーダーのユーザーは、問題がスクリーン リーダーの誤用に関連している間にスクリーン リーダーのバグが発生したと見なす場合があります。</span><span class="sxs-lookup"><span data-stu-id="c68f6-153">A novice screen reader user may assume that a screen reader bug has occurred while the issue is related to misuse of the screen reader.</span></span>  

<span data-ttu-id="c68f6-154">支援技術によるテストの学習の詳細については、「WebAIM[][WebaimArticlesScreenreaderTesting]のスクリーン リーダーによるテスト」に移動してください。</span><span class="sxs-lookup"><span data-stu-id="c68f6-154">For more information about learning to test with assistive technologies, navigate to [Testing with Screen Readers][WebaimArticlesScreenreaderTesting] on WebAIM.</span></span>  

### <span data-ttu-id="c68f6-155">ローカルでのテスト</span><span class="sxs-lookup"><span data-stu-id="c68f6-155">Testing Locally</span></span>  

<span data-ttu-id="c68f6-156">ほとんどのデバイスには、OS に組み込まれる支援技術が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-156">Most devices include assistive technology that is built-in to the OS.</span></span>  <span data-ttu-id="c68f6-157">Microsoft Windows には [、Windows ナレーター スクリーン リーダー][MicrosoftSupport22798] と Windows [拡大鏡が含まれています][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。</span><span class="sxs-lookup"><span data-stu-id="c68f6-157">Microsoft Windows includes the [Windows Narrator][MicrosoftSupport22798] screen reader and [Windows Magnifier][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198].</span></span>  <span data-ttu-id="c68f6-158">[NVDA、FreedomscientificSoftwareJaws、ZoomText]などのサードパーティの支援技術を[][FreedomscientificSoftwareZoomtext]ダウンロードできます。 [][NvaccessAboutNvda]</span><span class="sxs-lookup"><span data-stu-id="c68f6-158">3rd party assistive technologies like [NVDA][NvaccessAboutNvda], [FreedomscientificSoftwareJaws], and [ZoomText][FreedomscientificSoftwareZoomtext] are available to download.</span></span>  <span data-ttu-id="c68f6-159">Apple macOS には [VoiceOver スクリーン リーダー][AppleAccessibilityMacVision] が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-159">Apple macOS includes the [VoiceOver][AppleAccessibilityMacVision] screen reader.</span></span>  <span data-ttu-id="c68f6-160">また、iOS、Android、Linux はすべて、さまざまな支援技術をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-160">And iOS, Android, and Linux all support a variety of assistive technologies.</span></span>  

### <span data-ttu-id="c68f6-161">仮想マシンとエミュレーターでのテスト</span><span class="sxs-lookup"><span data-stu-id="c68f6-161">Testing in Virtual Machines and Emulators</span></span>  

<span data-ttu-id="c68f6-162">macOS では、Windows ナレーターや NVDA など、Windows でのみ利用可能な支援技術でテストする場合は、Windows 仮想マシンを作成します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-162">Under macOS, if you want to test with an assistive technology only available for Windows, like Windows Narrator or NVDA, create a Windows virtual machine.</span></span>  <span data-ttu-id="c68f6-163">Microsoft Edge \(EdgeHTML\) と IE を持つ仮想マシンは、仮想マシンのダウンロード ページで VirtualBox と VMWare [で利用できます][MicrosoftDeveloperEdgeVms]。</span><span class="sxs-lookup"><span data-stu-id="c68f6-163">Virtual machines with Microsoft Edge \(EdgeHTML\) and IE are available for VirtualBox and VMWare on the [Virtual Machines download page][MicrosoftDeveloperEdgeVms].</span></span>  

<span data-ttu-id="c68f6-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] には、Android アクセシビリティ スイートで支援技術をテストするエミュレーター [が含まれています][GooglePlayStoreAndroidAccessibilitySuite]。</span><span class="sxs-lookup"><span data-stu-id="c68f6-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] includes an emulator that for you to test assistive technologies in the [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite].</span></span>  <span data-ttu-id="c68f6-165">指示に従 [って仮想デバイス][AndroidDeveloperDevicesManagingAvdsHtml] をセットアップ [し、エミュレーター][AndroidDeveloperDevicesEmulatorHtml]を起動し、GooglePlay ストアから Android アクセシビリティ [スイート][GooglePlayStoreAndroidAccessibilitySuite] をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c68f6-165">Follow the instructions to [set up a virtual device][AndroidDeveloperDevicesManagingAvdsHtml] and [start the emulator][AndroidDeveloperDevicesEmulatorHtml], then install [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite] from the GooglePlay store.</span></span>  

> [!NOTE]
> <span data-ttu-id="c68f6-166">現在、iOS シミュレーターには VoiceOver は含めではありません。</span><span class="sxs-lookup"><span data-stu-id="c68f6-166">The iOS Simulator does not currently include VoiceOver.</span></span>  

### <span data-ttu-id="c68f6-167">クラウドベースのテスト ツール</span><span class="sxs-lookup"><span data-stu-id="c68f6-167">Cloud-based Testing Tools</span></span>  

<span data-ttu-id="c68f6-168">OS で支援技術が利用できない場合や、仮想マシンやエミュレーターにインストールできない場合は、次に最適なツールはクラウド ベースの支援技術テスト ツールです。</span><span class="sxs-lookup"><span data-stu-id="c68f6-168">If an assistive technology is not available on your OS or you not possible to install one on a virtual machine or emulator, cloud-based assistive technology testing tools are the next best thing.</span></span>  

*   <span data-ttu-id="c68f6-169">[Assistiv Labs (商用)][AssistivlabsMain] を使用すると、最新の Web ブラウザーを使用して支援技術を手動でテストできます。</span><span class="sxs-lookup"><span data-stu-id="c68f6-169">[Assistiv Labs (commercial)][AssistivlabsMain] enables you to manually test with assistive technologies through any modern web browser.</span></span>  <span data-ttu-id="c68f6-170">支援技術とブラウザーを選択し、操作する可能性のある仮想マシン、エミュレーター、または実際のデバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-170">Choose an assistive technology and browser and it connects you with a virtual machine, emulator, or real device with which you may interact.</span></span>  

## <span data-ttu-id="c68f6-171">リソース</span><span class="sxs-lookup"><span data-stu-id="c68f6-171">Resources</span></span>

### <span data-ttu-id="c68f6-172">アクセシビリティの基本</span><span class="sxs-lookup"><span data-stu-id="c68f6-172">Accessibility Basics</span></span>

#### [<span data-ttu-id="c68f6-173">A11Y プロジェクト</span><span class="sxs-lookup"><span data-stu-id="c68f6-173">The A11Y Project</span></span>](http://a11yproject.com/)

<span data-ttu-id="c68f6-174">A11Y プロジェクトは、Web アクセシビリティを容易にするためのコミュニティ型の取り組みです。</span><span class="sxs-lookup"><span data-stu-id="c68f6-174">The A11Y Project is a community-driven effort to make web accessibility easier.</span></span> <span data-ttu-id="c68f6-175">[A11Y プロジェクト](https://a11yproject.com/)サイトで、基本的なアクセシビリティの原則、アクセシビリティ 対応のパターンとウィジェット[](https://a11yproject.com/patterns)ライブラリ、アクセシビリティ[](http://a11yproject.com/resources.html)ソフトウェア、ブログ、書籍、ツールに関するリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-175">Check out [The A11Y Project](https://a11yproject.com/) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>

#### [<span data-ttu-id="c68f6-176">Web Accessibility Initiative (INITIATIVE)</span><span class="sxs-lookup"><span data-stu-id="c68f6-176">Web Accessibility Initiative (WAI)</span></span>](https://w3.org/WAI/)

<span data-ttu-id="c68f6-177">W3C Web Accessibility Initiative (INITIATIVE) は、Web のアクセシビリティを向上させる取り組みです。</span><span class="sxs-lookup"><span data-stu-id="c68f6-177">The W3C Web Accessibility Initiative (WAI) is an effort to help improve the accessibility of the web.</span></span> <span data-ttu-id="c68f6-178">サイトには[、Web](https://www.w3.org/WAI/gettingstarted/Overview.html)アクセシビリティの使用の開始、包含のための設計、チュートリアルや[](https://www.w3.org/WAI/users/Overview.html)プレゼンテーションなど、さまざまなリソース[](https://www.w3.org/WAI/train.html)が提供されています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-178">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>

### <span data-ttu-id="c68f6-179">アクセシビリティに関するブログ</span><span class="sxs-lookup"><span data-stu-id="c68f6-179">Accessibility Blogs</span></span>

#### [<span data-ttu-id="c68f6-180">Paciello グループ</span><span class="sxs-lookup"><span data-stu-id="c68f6-180">The Paciello Group</span></span>](https://www.paciellogroup.com/blog/)

<span data-ttu-id="c68f6-181">Paciello グループは、世界中の組織にコンサルティングおよびテクノロジ ソリューションを提供し、クライアントがすべての対象ユーザーに効果的かつ効率的に到達し、同時に政府および国際基準を満たします。</span><span class="sxs-lookup"><span data-stu-id="c68f6-181">The Paciello Group provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span> <span data-ttu-id="c68f6-182">ブログでは、Web アクセシビリティのベスト プラクティス、アクセシビリティ ツール、アクセシビリティの傾向などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-182">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>

#### [<span data-ttu-id="c68f6-183">単純にアクセス可能</span><span class="sxs-lookup"><span data-stu-id="c68f6-183">Simply Accessible</span></span>](http://simplyaccessible.com/articles/)

<span data-ttu-id="c68f6-184">Simply Accessible は、アクセシビリティ トレーニングやコンサルティングなど、Web 上のアクセシビリティの認識を変えるアクセシビリティ スペシャリストのチームです。</span><span class="sxs-lookup"><span data-stu-id="c68f6-184">Simply Accessible is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span> <span data-ttu-id="c68f6-185">「 [記事」](http://simplyaccessible.com/articles/) セクションでは、Web アクセシビリティ、アクセシビリティ対応の設計などについてのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-185">Their [Articles](http://simplyaccessible.com/articles/) section discusses best practices for web accessibility, accessible design, and more.</span></span>

#### [<span data-ttu-id="c68f6-186">SSB BART グループ (SSB)</span><span class="sxs-lookup"><span data-stu-id="c68f6-186">SSB BART Group (SSB)</span></span>](http://www.ssbbartgroup.com/blog/)

<span data-ttu-id="c68f6-187">SSB BART グループは、アクセシビリティ対応の製品とサービスの開発と展開を顧客にサポートするデジタル アクセシビリティ企業です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-187">SSB BART Group is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span> <span data-ttu-id="c68f6-188">ブログでは、ARIA のベスト プラクティス、アクセシビリティの傾向、ウェビナーなどについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-188">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>

### <span data-ttu-id="c68f6-189">Accessible Examples</span><span class="sxs-lookup"><span data-stu-id="c68f6-189">Accessible Examples</span></span>

#### [<span data-ttu-id="c68f6-190">ally.js - チュートリアル</span><span class="sxs-lookup"><span data-stu-id="c68f6-190">ally.js - Tutorials</span></span>](http://allyjs.io/tutorials/)

<span data-ttu-id="c68f6-191">アクセシビリティを簡単にすることで、アクセシビリティに関する最新の Web アプリケーションを支援する JavaScript ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="c68f6-191">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>

#### [<span data-ttu-id="c68f6-192">Heydonworks - ARIA の例</span><span class="sxs-lookup"><span data-stu-id="c68f6-192">Heydonworks - ARIA Examples</span></span>](http://heydonworks.com/practical_aria_examples/)

<span data-ttu-id="c68f6-193">アプリケーションのアクセシビリティを強化する実用的な ARIA の例</span><span class="sxs-lookup"><span data-stu-id="c68f6-193">Practical ARIA examples to enhance your application accessibility</span></span>

#### [<span data-ttu-id="c68f6-194">OpenAjax の例</span><span class="sxs-lookup"><span data-stu-id="c68f6-194">OpenAjax Examples</span></span>](http://oaa-accessibility.org/)

<span data-ttu-id="c68f6-195">OpenAjax Alliance の Web サイトは、RIA-ARIA の規則を検証する優れたリソースであり、なにかの一例を示しています。</span><span class="sxs-lookup"><span data-stu-id="c68f6-195">The OpenAjax Alliance website is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>

#### [<span data-ttu-id="c68f6-196">パターン</span><span class="sxs-lookup"><span data-stu-id="c68f6-196">Patterns</span></span>](http://a11yproject.com/patterns.html)

<span data-ttu-id="c68f6-197">[A11Y プロジェクトは](http://a11yproject.com/) 、メニュー、ボタン、ヒントなど、アクセス可能なウィジェットとパターンのライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-197">[The A11Y Project](http://a11yproject.com/) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>

### <span data-ttu-id="c68f6-198">アクセシビリティの手法と&ツール</span><span class="sxs-lookup"><span data-stu-id="c68f6-198">Accessibility Techniques & Tools</span></span>

#### [<span data-ttu-id="c68f6-199">アクセシビリティ: Microsoft Edge のアクセシビリティ対応の拡張機能アイコンの作成</span><span class="sxs-lookup"><span data-stu-id="c68f6-199">Accessibility: Creating accessible extension icons for Microsoft Edge</span></span>](../../edgehtml/extensions/guides/accessibility.md)

<span data-ttu-id="c68f6-200">Microsoft Edge のアクセス可能な拡張機能アイコンの作成に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-200">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>

#### [<span data-ttu-id="c68f6-201">アクセス可能な名前と説明: 計算とマッピング 1.1</span><span class="sxs-lookup"><span data-stu-id="c68f6-201">Accessible Name and Description: Computation and Mappings 1.1</span></span>](https://www.w3.org/TR/accname-1.1/)

<span data-ttu-id="c68f6-202">この W3C マッピング ドキュメントでは、Web コンテンツ言語からアクセス可能なオブジェクトの名前と説明をブラウザーが決定し、アクセシビリティ API で公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-202">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>

#### [<span data-ttu-id="c68f6-203">アクセシビリティ評価リソース</span><span class="sxs-lookup"><span data-stu-id="c68f6-203">Accessibility Evaluation Resources</span></span>](https://www.w3.org/WAI/eval/Overview.html)

<span data-ttu-id="c68f6-204">アクセシビリティ評価リソースは、アクセシビリティを考慮して Web サイトを評価するためのさまざまなアプローチの概要を示す、W3C によるマルチページ リソースです。</span><span class="sxs-lookup"><span data-stu-id="c68f6-204">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>

#### [<span data-ttu-id="c68f6-205">支援技術の互換性テスト</span><span class="sxs-lookup"><span data-stu-id="c68f6-205">Assistive technology compatibility tests</span></span>](http://www.powermapper.com/tests/)

<span data-ttu-id="c68f6-206">スクリーン リーダーのような支援技術 (AT) で異なるコンテンツ タイプと標準がどのように動作するのかを示すテスト結果。</span><span class="sxs-lookup"><span data-stu-id="c68f6-206">Test results showing how different content types and standards behave in assistive technologies (AT) like screen readers.</span></span>

#### [<span data-ttu-id="c68f6-207">アクセス可能な Web サイトの構築が簡単になりました</span><span class="sxs-lookup"><span data-stu-id="c68f6-207">Building accessible websites just got a lot easier</span></span>](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)

<span data-ttu-id="c68f6-208">この .NET Web 開発とツールのブログ投稿では、Web アクセシビリティ チェックのVisual Studio [について説明します](https://go.microsoft.com/fwlink/p/?linkid=841539)。</span><span class="sxs-lookup"><span data-stu-id="c68f6-208">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://go.microsoft.com/fwlink/p/?linkid=841539).</span></span>

#### [<span data-ttu-id="c68f6-209">コア アクセシビリティ API マッピング 1.1</span><span class="sxs-lookup"><span data-stu-id="c68f6-209">Core Accessibility API Mappings 1.1</span></span>](https://www.w3.org/TR/core-aam-1.1/)

<span data-ttu-id="c68f6-210">この W3C マッピング ドキュメントでは、Web コンテンツ言語のセマンティクスがアクセシビリティ API に公開される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-210">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  

#### [<span data-ttu-id="c68f6-211">簡単なチェック – Web アクセシビリティの最初のレビュー</span><span class="sxs-lookup"><span data-stu-id="c68f6-211">Easy Checks – A First Review of Web Accessibility</span></span>](https://www.w3.org/WAI/eval/preliminary.html)

<span data-ttu-id="c68f6-212">WEB ページのアクセシビリティに対応するのに役立つ、一連の QUICK Checks が、THE を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="c68f6-212">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>

#### [<span data-ttu-id="c68f6-213">WCAG 2.0 を満たす方法</span><span class="sxs-lookup"><span data-stu-id="c68f6-213">How to Meet WCAG 2.0</span></span>](https://www.w3.org/WAI/WCAG20/quickref/)

<span data-ttu-id="c68f6-214">Web コンテンツ アクセシビリティ ガイドライン (WCAG) 2.0 の要件 (成功基準) と手法のクイック リファレンスです。</span><span class="sxs-lookup"><span data-stu-id="c68f6-214">A quick reference to Web Content Accessibility Guidelines (WCAG) 2.0 requirements (success criteria) and techniques.</span></span>

#### [<span data-ttu-id="c68f6-215">HTML アクセシビリティ API マッピング 1.0</span><span class="sxs-lookup"><span data-stu-id="c68f6-215">HTML Accessibility API Mappings 1.0</span></span>](https://www.w3.org/TR/html-aam-1.0/)

<span data-ttu-id="c68f6-216">この W3C マッピング ドキュメントでは、HTML5.1 要素と属性をプラットフォーム アクセシビリティ API にマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-216">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>

#### [<span data-ttu-id="c68f6-217">クイック ヒント</span><span class="sxs-lookup"><span data-stu-id="c68f6-217">Quick Tips</span></span>](http://a11yproject.com/#Quick-tips)

<span data-ttu-id="c68f6-218">A11Y プロジェクトによるアクセシビリティに関するクイック [Web 開発のヒントの一覧](http://a11yproject.com/)です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-218">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com/).</span></span>

#### [<span data-ttu-id="c68f6-219">サイト スキャン</span><span class="sxs-lookup"><span data-stu-id="c68f6-219">Site Scan</span></span>](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)

<span data-ttu-id="c68f6-220">Microsoft Edge デベロッパー センターのサイト スキャン ツールは、古いライブラリ、レイアウトの問題、アクセシビリティの問題をチェックします。</span><span class="sxs-lookup"><span data-stu-id="c68f6-220">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>

#### [<span data-ttu-id="c68f6-221">WCAG 2.0 の手法</span><span class="sxs-lookup"><span data-stu-id="c68f6-221">Techniques for WCAG 2.0</span></span>](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)

<span data-ttu-id="c68f6-222">Web コンテンツ アクセシビリティ ガイドライン [(WCAG) 2.0](https://w3.org/TR/WCAG20/) の成功基準を満たす Web 開発者向けのガイダンスを提供する W3C の手法。</span><span class="sxs-lookup"><span data-stu-id="c68f6-222">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20/) success criteria.</span></span>

#### [<span data-ttu-id="c68f6-223">Web アクセシビリティの開発に関するヒント</span><span class="sxs-lookup"><span data-stu-id="c68f6-223">Tips on Developing for Web Accessibility</span></span>](https://w3.org/WAI/gettingstarted/tips/developing.html)

<span data-ttu-id="c68f6-224">障がいのある方がアクセスしやすい Web コンテンツの開発に関する W3C からのヒント。</span><span class="sxs-lookup"><span data-stu-id="c68f6-224">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>

#### [<span data-ttu-id="c68f6-225">RIA-ARIA Authoring Practices 1.1</span><span class="sxs-lookup"><span data-stu-id="c68f6-225">WAI-ARIA Authoring Practices 1.1</span></span>](http://w3c.github.io/aria-practices/)

<span data-ttu-id="c68f6-226">W3C のドキュメント。READERS-ARIA 1.1 の使い方を読者に理解し、WIDGETS-ARIA の役割、状態、およびプロパティを使用してウィジェット、ナビゲーション、および動作にアクセス可能な方法を推奨します。</span><span class="sxs-lookup"><span data-stu-id="c68f6-226">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>

#### [<span data-ttu-id="c68f6-227">GUIDELINE のガイドラインと手法</span><span class="sxs-lookup"><span data-stu-id="c68f6-227">WAI Guidelines and Techniques</span></span>](https://w3.org/WAI/guid-tech.html)

<span data-ttu-id="c68f6-228">一連の Web アクセシビリティ ガイドラインと、ANDSY が開発した標準。</span><span class="sxs-lookup"><span data-stu-id="c68f6-228">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  

#### [<span data-ttu-id="c68f6-229">Web アクセシビリティ評価ツールの一覧</span><span class="sxs-lookup"><span data-stu-id="c68f6-229">Web Accessibility Evaluation Tools List</span></span>](https://www.w3.org/WAI/ER/tools/index.html)

<span data-ttu-id="c68f6-230">Web サイトがアクセシビリティ ガイドラインを満たしたかどうかを判断するのに役立つ Web アクセシビリティ評価ツールの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c68f6-230">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>

#### [<span data-ttu-id="c68f6-231">Web アクセシビリティの観点: すべてのユーザーに対する影響と利点を探る</span><span class="sxs-lookup"><span data-stu-id="c68f6-231">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>](https://w3.org/WAI/perspectives/)

<span data-ttu-id="c68f6-232">アクセシビリティの影響とすべてのユーザーに対するメリットに関する W3C による一連の短い状況に関するビデオ。</span><span class="sxs-lookup"><span data-stu-id="c68f6-232">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "仮想マシン |Microsoft Edge 開発者"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 "ナレーターの完全なガイド |Microsoft サポート"  
[MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]: https://support.microsoft.com/windows/414948ba-8b1c-d3bd-8615-0e5e32204198 "拡大鏡を使って画面の表示を簡単にする |Microsoft サポート"  

[AccessibilityinsightsWebOverview]: https://accessibilityinsights.io/docs/web/overview "Web 用のアクセシビリティインサイト |アクセシビリティに関するインサイト"  

[AndroidDeveloperDevicesManagingAvdsHtml]: https://developer.android.com/tools/devices/managing-avds.html "仮想デバイスの作成と管理 |Android 開発者"  
[AndroidDeveloperDevicesEmulatorHtml]: https://developer.android.com/tools/devices/emulator.html "Android エミュレーターでアプリを実行する |Android 開発者"  
[AndroidDeveloperSdkInstallingStudioHtml]: https://developer.android.com/sdk/installing/studio.html "Android Studio をダウンロードする |Android 開発者"  

[AppleAccessibilityMacVision]: https://www.apple.com/accessibility/mac/vision "視覚アクセシビリティ - Mac |Apple"  

[AssistivlabsMain]: https://assistivlabs.com "Assistiv Labs"  

[FreedomscientificSoftwareJaws]: https://www.freedomscientific.com/products/software/jaws "JAWS® |Freedom Scientific"  
[FreedomscientificSoftwareZoomtext]: https://www.freedomscientific.com/products/software/zoomtext "ZoomText |Freedom Scientific"  

[GooglePlayStoreAndroidAccessibilitySuite]: https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback "Android アクセシビリティ スイート |GooglePlay ストア"  

[NvaccessAboutNvda]: https://www.nvaccess.org/about-nvda "NVDA について |NV Access"  

[W3cPerspectiveVideosKeyboard]: https://www.w3.org/WAI/perspective-videos/keyboard "キーボードの互換性 |W3C"  

[WebaimProjectsLowvisionsurvey2]: https://webaim.org/projects/lowvisionsurvey2 "低ビジョンのユーザーに関するアンケート \#2結果 |WebAIM"  
[WebaimProjectsScreenreadersurvey8]: https://webaim.org/projects/screenreadersurvey8 "スクリーン リーダー ユーザー アンケート \#8結果 |WebAIM"  
[WebaimArticlesScreenreaderTesting]: https://webaim.org/articles/screenreader_testing "スクリーン リーダーを使用したテスト |WebAIM"  
