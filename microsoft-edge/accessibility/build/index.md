---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: ベスト プラクティスと Accessible Rich Internet Applications (ARIA) を組み合わせて、アクセス可能な Web サイトを作成する方法について説明します。
title: ビルド |アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 99f0eb9d96bc6d53df72839c6c2f1e61cbd5494e
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564022"
---
# <a name="building-accessible-websites"></a><span data-ttu-id="98d0c-104">アクセス可能な Web サイトの構築</span><span class="sxs-lookup"><span data-stu-id="98d0c-104">Building Accessible Websites</span></span>  

<span data-ttu-id="98d0c-105">Web には、HTML、CSS、JavaScript の組み合わせを使用して構築された動的で複雑な Web サイト、アプリケーション、およびユーザー インターフェイスが埋め込みされています。</span><span class="sxs-lookup"><span data-stu-id="98d0c-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="98d0c-106">ただし、アクセシビリティを念頭に置いて設計および構築した場合、これらの複雑な Web サイトは、支援[](https://webaim.org/articles/motor/assistive)テクノロジを使用して Web を閲覧するユーザーが使用することは困難です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span>  <span data-ttu-id="98d0c-107">障がい者がアクセスできる Web サイトを構築するには、ユーザー インターフェイスに関するセマンティックな情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span>  <span data-ttu-id="98d0c-108">これにより、スクリーン リーダーなどの支援テクノロジは、さまざまな機能を持つユーザーが Web サイトを使用するのに役立つ必要な情報を伝えます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>  

<span data-ttu-id="98d0c-109">[HTML5Accessibility に](https://html5accessibility.com)アクセスして、ユーザーがサポートする新しい HTML5 機能に関する情報Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="98d0c-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>  

## <a name="how-accessibility-works"></a><span data-ttu-id="98d0c-110">アクセシビリティのしくみ</span><span class="sxs-lookup"><span data-stu-id="98d0c-110">How Accessibility Works</span></span>  

<span data-ttu-id="98d0c-111">支援テクノロジは、通常はコンピューターにはない機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-111">Assistive technologies add capabilities that computers don't usually have.</span></span>  <span data-ttu-id="98d0c-112">たとえば、視覚障害のあるユーザーは、マウスと画面でブラウザーを直接使用するのではなく、スクリーン リーダーなどの支援テクノロジと組み合わせてキーボードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span>  <span data-ttu-id="98d0c-113">Microsoft プラットフォームおよび Web 上のアプリケーションの場合、支援テクノロジは Microsoft [UI オートメーション](/windows/win32/winauto/uiauto-specandcommunitypromise)、Microsoft Edge の Document Object Model \(DOM\) などのアプリケーション固有のオブジェクト モデル、またはこれらの組み合わせと対話します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](/windows/win32/winauto/uiauto-specandcommunitypromise), an application-specific object model such as the Document Object Model \(DOM\) in Microsoft Edge, or a combination of these.</span></span>  

<span data-ttu-id="98d0c-114">Web 開発者の場合、特定の HTML 要素は UI オートメーション オブジェクトにマップされます。そのため、これらの HTML 要素を選択する場合、開発者はそれらの要素に組み込みのアクセシビリティ プロパティとイベントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span>  <span data-ttu-id="98d0c-115">Web サイトを開発する場合、アプリケーションにアクセスするには、通常、API が \(または適切な要素が指定\) に正しく書き込まれるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d0c-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to \(or that the appropriate element is specified\), in order for the application to be accessible.</span></span>  <span data-ttu-id="98d0c-116">詳細については[、「ARIA と UI オートメーション」Microsoft Edge](./aria-and-ui-automation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98d0c-116">Check out [ARIA and UI Automation in Microsoft Edge](./aria-and-ui-automation.md) for more information.</span></span>  <span data-ttu-id="98d0c-117">アクセス可能なユニバーサル Windows プラットフォーム \(UWP\) アプリの詳細については、「アクセシビリティ[](/windows/uwp/design/accessibility/accessibility)」のトピックWindows デベロッパー センター。</span><span class="sxs-lookup"><span data-stu-id="98d0c-117">For information on accessible Universal Windows Platform \(UWP\) apps, navigate to the [Accessibility](/windows/uwp/design/accessibility/accessibility) topic in the Windows Dev Center.</span></span>  

<span data-ttu-id="98d0c-118">動的コンテンツに関する多くの一般的なアクセシビリティの問題は、適切なコーディング方法によって解決できます。 [また、WCAG 2.0](https://www.w3.org/TR/WCAG20) のドキュメントには、よりアクセスしやすい動的 Web アプリケーションを作成するための多くの手法とベスト プラクティスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="98d0c-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://www.w3.org/TR/WCAG20) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span>  <span data-ttu-id="98d0c-119">ただし、適切にコード化された場合でも、動的コンテンツにアクセスできるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="98d0c-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span>  <span data-ttu-id="98d0c-120">[アクセス可能なリッチ インターネット アプリケーション (ARIA) は、この](#aria) 問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="98d0c-121">Web アクセシビリティの詳細については、「Web アクセシビリティ[](https://www.w3.org/WAI/intro/accessibility.php)イニシアティブ (WAI) による Web アクセシビリティの概要[」を参照してください](https://www.w3.org/WAI)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI).</span></span>  

## <a name="aria"></a><span data-ttu-id="98d0c-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="98d0c-122">ARIA</span></span>  

<span data-ttu-id="98d0c-123">W3C の Web アクセシビリティ イニシアティブによるアクセシビリティ対応リッチ インターネット[](https://www.w3.org/WAI)アプリケーション[(ARIA)](https://www.w3.org/TR/wai-aria)仕様は、動的 Web コンテンツとカスタム ユーザー インターフェイスをすべてのユーザーがアクセス可能にするための構文として定義されています。</span><span class="sxs-lookup"><span data-stu-id="98d0c-123">The [Accessible Rich Internet Applications (ARIA)](https://www.w3.org/TR/wai-aria) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span>  <span data-ttu-id="98d0c-124">ARIA は、カスタム セマンティクスを伝えるために設計された追加の属性 \(roles, properties, and states\) を使用して HTML を拡張します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-124">ARIA extends HTML by using additional attributes \(roles, properties, and states\) that are designed to convey custom semantics.</span></span>  <span data-ttu-id="98d0c-125">これらの属性は、ブラウザーがコントロールの状態と役割をアクセシビリティ API に渡す場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>  

### <a name="roles-properties-and-states"></a><span data-ttu-id="98d0c-126">ロール、プロパティ、および状態</span><span class="sxs-lookup"><span data-stu-id="98d0c-126">Roles, Properties, and States</span></span>  

<span data-ttu-id="98d0c-127">ARIA の役割は [、role](https://developer.mozilla.org/docs/Web/HTML/Reference) 属性を使用して要素に設定され、その要素に関する支援テクノロジとアクセシビリティ API 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-127">ARIA roles are set on elements using the [role](https://developer.mozilla.org/docs/Web/HTML/Reference) attribute to give assistive technologies and accessibility APIs information about the element.</span></span>  <span data-ttu-id="98d0c-128">たとえば、メニュー内のアイテムを示す次の要素が割 `<li>` `role="menuitem"` り当てられます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>  

```html
<li role="menuitem">Home</li>
```  

<span data-ttu-id="98d0c-129">ARIA の状態とプロパティは、ロールの性質の定義を形成するのに役立つオブジェクトに関する特定の情報を提供する、aria プレフィックス付き属性です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span>  <span data-ttu-id="98d0c-130">プロパティは [、aria-readonly や aria-haspopup](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) など、オブジェクトの性質に不可欠 [な属性です](https://developer.mozilla.org/docs/Web/Accessibility/ARIA)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-130">Properties are attributes that are essential to the nature of an object, like [aria-readonly](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) and [aria-haspopup](https://developer.mozilla.org/docs/Web/Accessibility/ARIA).</span></span>  <span data-ttu-id="98d0c-131">プロパティを変更すると、オブジェクトの意味に影響します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-131">Changing a property affects the meaning of the object.</span></span>  <span data-ttu-id="98d0c-132">次の例では、プロパティがメニュー項目に設定されている場合、ポップアップ `aria-haspopup="true"` `<li>` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>  

```html
<li role="menuitem" aria-haspopup="true">Open</li>
```  

<span data-ttu-id="98d0c-133">状態はオブジェクトの性質を変更しませんが、オブジェクトに関連付けられた情報や、オブジェクトとのユーザー操作 [(aria-hidden](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) や [aria-checked](https://developer.mozilla.org/docs/Web/Accessibility/ARIA)など) を表します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [aria-hidden](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) or [aria-checked](https://developer.mozilla.org/docs/Web/Accessibility/ARIA).</span></span>  <span data-ttu-id="98d0c-134">たとえば、次の `aria-checked="false"` 例の状態は、チェック ボックスがオフになっていることを表します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>  

```html
<div role="checkbox" aria-checked="false">Accept</div>
```  

<span data-ttu-id="98d0c-135">W3C [の [ロール モデル](https://www.w3.org/TR/wai-aria-1.1#roles) ] に移動して、役割、プロパティ、および状態の完全な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1#roles) by the W3C to see a full list of roles, properties, and states.</span></span>  

<span data-ttu-id="98d0c-136">ARIA の詳細については、「リソース」セクションの「ARIA」 [に移動](#resources) します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-136">For more information on ARIA, navigate to ARIA in the [Resources](#resources) section.</span></span>  

## <a name="assistive-technology-compatibility-testing"></a><span data-ttu-id="98d0c-137">支援テクノロジの互換性テスト</span><span class="sxs-lookup"><span data-stu-id="98d0c-137">Assistive Technology Compatibility Testing</span></span>  

<span data-ttu-id="98d0c-138">作成する Web サイトが実際の支援テクノロジで動作することの確認は、障害を持つユーザーに優れたエクスペリエンスを提供するための最良の方法です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-138">Verifying that the website you are building works with real assistive technologies is the best way to ensure a good experience for your users with disabilities.</span></span>  <span data-ttu-id="98d0c-139">多くの支援テクノロジがキーボードを利用していますので、Web サイトのキーボード アクセシビリティのテストを開始する際に便利です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-139">Since many assistive technologies make use of the keyboard, testing the keyboard accessibility of your website is a good place to start.</span></span>  <span data-ttu-id="98d0c-140">[キーボード互換性テストでは、][W3cPerspectiveVideosKeyboard] マウスを必要とせずにすべての対話型コントロールにアクセスできるユーザーを検証します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-140">[Keyboard compatibility testing][W3cPerspectiveVideosKeyboard] validates that users have access to all interactive controls without requiring a mouse.</span></span>  <span data-ttu-id="98d0c-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview]は、Microsoft Edgeおよび Chrome のブラウザー拡張機能であり、いくつかの一般的な問題を説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] is a browser extension for Microsoft Edge and Chrome that guides you and reveals several common issues.</span></span>  

<span data-ttu-id="98d0c-142">Web サイトがキーボードとうまく機能すると確信したら、スクリーン リーダーなどの他の支援テクノロジで試してみてください。</span><span class="sxs-lookup"><span data-stu-id="98d0c-142">Once you are confident that your website works well with a keyboard, try it with other assistive technologies, such as screen readers.</span></span>  <span data-ttu-id="98d0c-143">次の問題を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="98d0c-143">It uncover issues in the following.</span></span>  

*   <span data-ttu-id="98d0c-144">HTML、ARIA、CSS。</span><span class="sxs-lookup"><span data-stu-id="98d0c-144">Your HTML, ARIA, and CSS.</span></span>  
*   <span data-ttu-id="98d0c-145">機能または技術に対する支援技術のサポートレベル。</span><span class="sxs-lookup"><span data-stu-id="98d0c-145">The level of support of an assistive technology for a feature or technique.</span></span>  
    
<span data-ttu-id="98d0c-146">異なるブラウザーでは、プラットフォームアクセシビリティ API に要素をマップする方法が、ユーザー設定と異Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="98d0c-146">Different browsers may map elements to platform accessibility APIs differently than Microsoft Edge.</span></span>  <span data-ttu-id="98d0c-147">インターフェイスを構築する際には、それぞれの違いを考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-147">While building your interface, it is important to consider each difference.</span></span>  

<span data-ttu-id="98d0c-148">WebAIM では、スクリーン[][WebaimProjectsScreenreadersurvey8]リーダーと[][WebaimProjectsLowvisionsurvey2]低ビジョン ユーザーによるアンケートを実施し、テストする支援テクノロジとブラウザーを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-148">WebAIM conducts surveys with [screen reader][WebaimProjectsScreenreadersurvey8] and [low vision][WebaimProjectsLowvisionsurvey2] users that help you decide which assistive technologies and browsers you want to test.</span></span>  

### <a name="learning-how-to-test"></a><span data-ttu-id="98d0c-149">テスト方法の学習</span><span class="sxs-lookup"><span data-stu-id="98d0c-149">Learning How to Test</span></span>  

<span data-ttu-id="98d0c-150">支援技術は高度なツールです。</span><span class="sxs-lookup"><span data-stu-id="98d0c-150">Assistive technologies are sophisticated tools.</span></span>  <span data-ttu-id="98d0c-151">支援技術を使用してテストをすぐに開始できると仮定して、最初に動作を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d0c-151">Do not assume that you are able to immediately start testing with an assistive technology without first learning about how it works.</span></span>  <span data-ttu-id="98d0c-152">スクリーン リーダーを使ってテストする方法は、特に急な学習曲線です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-152">Learning to test with a screen reader has an especially steep learning curve.</span></span>  <span data-ttu-id="98d0c-153">初心者のスクリーン リーダー ユーザーは、問題がスクリーン リーダーの誤用に関連している間にスクリーン リーダーのバグが発生したと考える場合があります。</span><span class="sxs-lookup"><span data-stu-id="98d0c-153">A novice screen reader user may assume that a screen reader bug has occurred while the issue is related to misuse of the screen reader.</span></span>  

<span data-ttu-id="98d0c-154">支援テクノロジによるテストの学習の詳細については、「WebAIM のスクリーン リーダーによるテスト [」][WebaimArticlesScreenreaderTesting] に移動します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-154">For more information about learning to test with assistive technologies, navigate to [Testing with Screen Readers][WebaimArticlesScreenreaderTesting] on WebAIM.</span></span>  

### <a name="testing-locally"></a><span data-ttu-id="98d0c-155">ローカルでのテスト</span><span class="sxs-lookup"><span data-stu-id="98d0c-155">Testing Locally</span></span>  

<span data-ttu-id="98d0c-156">ほとんどのデバイスには、OS に組み込まれる支援テクノロジが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-156">Most devices include assistive technology that is built-in to the OS.</span></span>  <span data-ttu-id="98d0c-157">Microsoft Windowsには、スクリーン リーダー [Windows ナレーター][MicrosoftSupport22798]拡大鏡Windows[があります][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。</span><span class="sxs-lookup"><span data-stu-id="98d0c-157">Microsoft Windows includes the [Windows Narrator][MicrosoftSupport22798] screen reader and [Windows Magnifier][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198].</span></span>  <span data-ttu-id="98d0c-158">[NVDA、FreedomscientificSoftwareJaws、ZoomText]などのサードパーティの支援テクノロジを[][FreedomscientificSoftwareZoomtext]ダウンロードできます。 [][NvaccessAboutNvda]</span><span class="sxs-lookup"><span data-stu-id="98d0c-158">3rd party assistive technologies like [NVDA][NvaccessAboutNvda], [FreedomscientificSoftwareJaws], and [ZoomText][FreedomscientificSoftwareZoomtext] are available to download.</span></span>  <span data-ttu-id="98d0c-159">Apple macOS には [VoiceOver スクリーン リーダーが][AppleAccessibilityMacVision] 含まれています。</span><span class="sxs-lookup"><span data-stu-id="98d0c-159">Apple macOS includes the [VoiceOver][AppleAccessibilityMacVision] screen reader.</span></span>  <span data-ttu-id="98d0c-160">iOS、Android、Linux はすべて、さまざまな支援テクノロジをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="98d0c-160">And iOS, Android, and Linux all support a variety of assistive technologies.</span></span>  

### <a name="testing-in-virtual-machines-and-emulators"></a><span data-ttu-id="98d0c-161">仮想マシンとエミュレーターでのテスト</span><span class="sxs-lookup"><span data-stu-id="98d0c-161">Testing in Virtual Machines and Emulators</span></span>  

<span data-ttu-id="98d0c-162">macOS では、Windows や NVDA など、Windows Windows ナレーター でのみ使用できる支援テクノロジでテストする場合は、Windows 仮想マシンを作成します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-162">Under macOS, if you want to test with an assistive technology only available for Windows, like Windows Narrator or NVDA, create a Windows virtual machine.</span></span>  <span data-ttu-id="98d0c-163">\(EdgeHTML\) Microsoft Edge IE を持つ仮想マシンは、[仮想マシン] ダウンロード ページの VirtualBox および VMWare[で使用できます][MicrosoftDeveloperEdgeVms]。</span><span class="sxs-lookup"><span data-stu-id="98d0c-163">Virtual machines with Microsoft Edge \(EdgeHTML\) and IE are available for VirtualBox and VMWare on the [Virtual Machines download page][MicrosoftDeveloperEdgeVms].</span></span>  

<span data-ttu-id="98d0c-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] には、Android アクセシビリティ スイートで支援テクノロジをテストする [エミュレーターが含まれています][GooglePlayStoreAndroidAccessibilitySuite]。</span><span class="sxs-lookup"><span data-stu-id="98d0c-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] includes an emulator that for you to test assistive technologies in the [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite].</span></span>  <span data-ttu-id="98d0c-165">手順に従って仮想デバイスを[セットアップ][AndroidDeveloperDevicesManagingAvdsHtml]し、エミュレーター[][AndroidDeveloperDevicesEmulatorHtml]を起動し、GooglePlay ストアから[Android アクセシビリティ][GooglePlayStoreAndroidAccessibilitySuite]スイートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="98d0c-165">Follow the instructions to [set up a virtual device][AndroidDeveloperDevicesManagingAvdsHtml] and [start the emulator][AndroidDeveloperDevicesEmulatorHtml], then install [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite] from the GooglePlay store.</span></span>  

> [!NOTE]
> <span data-ttu-id="98d0c-166">iOS シミュレーターには、現在 VoiceOver は含めではありません。</span><span class="sxs-lookup"><span data-stu-id="98d0c-166">The iOS Simulator does not currently include VoiceOver.</span></span>  

### <a name="cloud-based-testing-tools"></a><span data-ttu-id="98d0c-167">クラウドベースのテスト ツール</span><span class="sxs-lookup"><span data-stu-id="98d0c-167">Cloud-based Testing Tools</span></span>  

<span data-ttu-id="98d0c-168">支援テクノロジが OS で使用できない場合、または仮想マシンまたはエミュレーターにインストールできない場合は、クラウドベースの支援技術テスト ツールが次に最適です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-168">If an assistive technology is not available on your OS or you not possible to install one on a virtual machine or emulator, cloud-based assistive technology testing tools are the next best thing.</span></span>  

*   <span data-ttu-id="98d0c-169">[Assistiv Labs (商用) を][AssistivlabsMain] 使用すると、最新の Web ブラウザーを介して支援テクノロジを手動でテストできます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-169">[Assistiv Labs (commercial)][AssistivlabsMain] enables you to manually test with assistive technologies through any modern web browser.</span></span>  <span data-ttu-id="98d0c-170">支援テクノロジとブラウザーを選択すると、操作できる仮想マシン、エミュレーター、または実際のデバイスに接続されます。</span><span class="sxs-lookup"><span data-stu-id="98d0c-170">Choose an assistive technology and browser and it connects you with a virtual machine, emulator, or real device with which you may interact.</span></span>  

## <a name="resources"></a><span data-ttu-id="98d0c-171">リソース</span><span class="sxs-lookup"><span data-stu-id="98d0c-171">Resources</span></span>  

### <a name="accessibility-basics"></a><span data-ttu-id="98d0c-172">アクセシビリティの基本</span><span class="sxs-lookup"><span data-stu-id="98d0c-172">Accessibility Basics</span></span>  

#### <a name="the-a11y-project"></a><span data-ttu-id="98d0c-173">A11Y Project</span><span class="sxs-lookup"><span data-stu-id="98d0c-173">The A11Y Project</span></span>  

<span data-ttu-id="98d0c-174">[A11Y Project](http://a11yproject.com)は、Web アクセシビリティを容易にするためのコミュニティ駆動型の取り組みです。</span><span class="sxs-lookup"><span data-stu-id="98d0c-174">[The A11Y Project](http://a11yproject.com) is a community-driven effort to make web accessibility easier.</span></span>  <span data-ttu-id="98d0c-175">[A11Y Project](https://a11yproject.com)サイトを参照して、アクセシビリティの基本的な原則、アクセシビリティ のパターンとウィジェット ライブラリ[](https://a11yproject.com/patterns)、アクセシビリティ ソフトウェア[](http://a11yproject.com/resources.html)、ブログ、書籍、ツールに関するリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-175">Check out [The A11Y Project](https://a11yproject.com) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>  

#### <a name="web-accessibility-initiative-wai"></a><span data-ttu-id="98d0c-176">Web アクセシビリティ イニシアチブ (WAI)</span><span class="sxs-lookup"><span data-stu-id="98d0c-176">Web Accessibility Initiative (WAI)</span></span>  

<span data-ttu-id="98d0c-177">W3C [Web アクセシビリティ イニシアチブ (WAI)](https://w3.org/WAI) は、Web のアクセシビリティを向上させる取り組みです。</span><span class="sxs-lookup"><span data-stu-id="98d0c-177">The W3C [Web Accessibility Initiative (WAI)](https://w3.org/WAI) is an effort to help improve the accessibility of the web.</span></span>  <span data-ttu-id="98d0c-178">サイトには [、Web](https://www.w3.org/WAI/gettingstarted/Overview.html)アクセシビリティの使い始 [め、包含](https://www.w3.org/WAI/users/Overview.html)の設計、チュートリアルとプレゼンテーションなど、さまざまな [リソースが](https://www.w3.org/WAI/train.html)提供されています。</span><span class="sxs-lookup"><span data-stu-id="98d0c-178">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>  

### <a name="accessibility-blogs"></a><span data-ttu-id="98d0c-179">アクセシビリティブログ</span><span class="sxs-lookup"><span data-stu-id="98d0c-179">Accessibility Blogs</span></span>  

#### <a name="tpgi-llc"></a><span data-ttu-id="98d0c-180">TPGi、LLC</span><span class="sxs-lookup"><span data-stu-id="98d0c-180">TPGi, LLC</span></span>  

<span data-ttu-id="98d0c-181">[TPGi、LLC](https://www.tpgi.com/blog) は、世界中の組織にコンサルティングとテクノロジ ソリューションを提供し、政府および国際基準を満たしながら、クライアントが効果的かつ効率的にすべての対象ユーザーに確実に到達します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-181">[TPGi, LLC](https://www.tpgi.com/blog) provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span>  <span data-ttu-id="98d0c-182">ブログでは、Web アクセシビリティのベスト プラクティス、アクセシビリティ ツール、アクセシビリティの傾向に関するトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-182">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>  

#### <a name="simply-accessible"></a><span data-ttu-id="98d0c-183">単純にアクセス可能</span><span class="sxs-lookup"><span data-stu-id="98d0c-183">Simply Accessible</span></span>  

<span data-ttu-id="98d0c-184">[Simply Accessible](http://simplyaccessible.com/articles) は、アクセシビリティトレーニング、コンサルティングなど、Web 上のアクセシビリティの認識を変えるアクセシビリティスペシャリストのチームです。</span><span class="sxs-lookup"><span data-stu-id="98d0c-184">[Simply Accessible](http://simplyaccessible.com/articles) is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span>  <span data-ttu-id="98d0c-185">[ [記事]](http://simplyaccessible.com/articles) セクションでは、Web アクセシビリティ、アクセス可能なデザインなどについてのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-185">Their [Articles](http://simplyaccessible.com/articles) section discusses best practices for web accessibility, accessible design, and more.</span></span>  

#### <a name="level-access"></a><span data-ttu-id="98d0c-186">レベル アクセス</span><span class="sxs-lookup"><span data-stu-id="98d0c-186">Level Access</span></span>  

<span data-ttu-id="98d0c-187">[Level Access](https://www.levelaccess.com/blog) は、アクセス可能な製品およびサービスの開発と展開におけるクライアントをサポートするデジタル アクセシビリティ企業です。</span><span class="sxs-lookup"><span data-stu-id="98d0c-187">[Level Access](https://www.levelaccess.com/blog) is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span>  <span data-ttu-id="98d0c-188">ブログでは、ARIA のベスト プラクティス、アクセシビリティの傾向、ウェビナーなどについて説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-188">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>  

### <a name="accessible-examples"></a><span data-ttu-id="98d0c-189">アクセス可能な例</span><span class="sxs-lookup"><span data-stu-id="98d0c-189">Accessible Examples</span></span>  

#### <a name="allyjs---tutorials"></a><span data-ttu-id="98d0c-190">ally.js - チュートリアル</span><span class="sxs-lookup"><span data-stu-id="98d0c-190">ally.js - Tutorials</span></span>  

<span data-ttu-id="98d0c-191">アクセシビリティを簡単にすることで、アクセシビリティに関する懸念を持つ最新の Web アプリケーションを支援する JavaScript ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="98d0c-191">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>  <span data-ttu-id="98d0c-192">詳細については、「ally.js [ - チュートリアル」に移動します](http://allyjs.io/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-192">For more information, navigate to [ally.js - Tutorials](http://allyjs.io/tutorials).</span></span>  

#### <a name="openajax-examples"></a><span data-ttu-id="98d0c-193">OpenAjax の例</span><span class="sxs-lookup"><span data-stu-id="98d0c-193">OpenAjax Examples</span></span>  

<span data-ttu-id="98d0c-194">[OpenAjax Alliance Web](http://oaa-accessibility.org)サイトは、WAI-ARIA のルールを検証する優れたリソースであり、WAI-ARIA 実装の例を多数提供します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-194">The [OpenAjax Alliance website](http://oaa-accessibility.org) is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>  

#### <a name="patterns"></a><span data-ttu-id="98d0c-195">パターン</span><span class="sxs-lookup"><span data-stu-id="98d0c-195">Patterns</span></span>  

<span data-ttu-id="98d0c-196">[A11Y Project](http://a11yproject.com)には、メニュー、ボタン、ツールヒントなど、アクセス可能なウィジェットやパターンのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="98d0c-196">[The A11Y Project](http://a11yproject.com) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>  <span data-ttu-id="98d0c-197">詳細については、「パターン」 [に移動します](http://a11yproject.com/patterns.html)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-197">For more information, navigate to [Patterns](http://a11yproject.com/patterns.html).</span></span>  

### <a name="accessibility-techniques--tools"></a><span data-ttu-id="98d0c-198">アクセシビリティの手法&ツール</span><span class="sxs-lookup"><span data-stu-id="98d0c-198">Accessibility Techniques & Tools</span></span>

#### <a name="accessibility--creating-accessible-extension-icons-for-microsoft-edge"></a><span data-ttu-id="98d0c-199">アクセシビリティ: ユーザー補助機能用のアクセス可能な拡張機能Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="98d0c-199">Accessibility:  Creating accessible extension icons for Microsoft Edge</span></span>  

<span data-ttu-id="98d0c-200">アクセス可能な拡張機能のアイコンを作成する方法については、Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="98d0c-200">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>  <span data-ttu-id="98d0c-201">詳細については、「アクセシビリティ: アクセス可能な拡張機能のアイコンを作成する」[に移動Microsoft Edge。](/archive/microsoft-edge/legacy/developer/extensions/guides/accessibility)</span><span class="sxs-lookup"><span data-stu-id="98d0c-201">For more information, navigate to [Accessibility: Creating accessible extension icons for Microsoft Edge](/archive/microsoft-edge/legacy/developer/extensions/guides/accessibility).</span></span>  

#### <a name="accessible-name-and-description-computation-and-mappings-11"></a><span data-ttu-id="98d0c-202">アクセス可能な名前と説明: 計算とマッピング 1.1</span><span class="sxs-lookup"><span data-stu-id="98d0c-202">Accessible Name and Description: Computation and Mappings 1.1</span></span>  

<span data-ttu-id="98d0c-203">この W3C マッピング ドキュメントでは、ブラウザーが Web コンテンツ言語からアクセス可能なオブジェクトの名前と説明を決定し、アクセシビリティ API で公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-203">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>  <span data-ttu-id="98d0c-204">詳細については、「アクセス可能な名前 [と説明: 計算とマッピング 1.1」に移動します](https://www.w3.org/TR/accname-1.1)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-204">For more information, navigate to [Accessible Name and Description: Computation and Mappings 1.1](https://www.w3.org/TR/accname-1.1).</span></span>  

#### <a name="accessibility-evaluation-resources"></a><span data-ttu-id="98d0c-205">アクセシビリティ評価リソース</span><span class="sxs-lookup"><span data-stu-id="98d0c-205">Accessibility Evaluation Resources</span></span>  

<span data-ttu-id="98d0c-206">アクセシビリティ評価リソースは、Web サイトでアクセシビリティを評価するためのさまざまな方法を概説する、W3C による複数ページのリソースです。</span><span class="sxs-lookup"><span data-stu-id="98d0c-206">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>  <span data-ttu-id="98d0c-207">詳細については、「アクセシビリティ評価リソース [」に移動します](https://www.w3.org/WAI/eval/Overview.html)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-207">For more information, navigate to [Accessibility Evaluation Resources](https://www.w3.org/WAI/eval/Overview.html).</span></span>  

#### <a name="assistive-technology-compatibility-tests"></a><span data-ttu-id="98d0c-208">支援テクノロジの互換性テスト</span><span class="sxs-lookup"><span data-stu-id="98d0c-208">Assistive technology compatibility tests</span></span>  

<span data-ttu-id="98d0c-209">スクリーン リーダーのような支援テクノロジ \(AT\) で異なるコンテンツ タイプと標準がどのように動作するのかを示すテスト結果。</span><span class="sxs-lookup"><span data-stu-id="98d0c-209">Test results showing how different content types and standards behave in assistive technologies \(AT\) like screen readers.</span></span>  <span data-ttu-id="98d0c-210">詳細については、「支援テクノロジの [互換性テスト」に移動します](http://www.powermapper.com/tests)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-210">For more information, navigate to [Assistive technology compatibility tests](http://www.powermapper.com/tests).</span></span>  

#### <a name="building-accessible-websites-just-got-a-lot-easier"></a><span data-ttu-id="98d0c-211">アクセス可能な Web サイトの構築がはるかに簡単になりました</span><span class="sxs-lookup"><span data-stu-id="98d0c-211">Building accessible websites just got a lot easier</span></span>  

<span data-ttu-id="98d0c-212">この .NET Web 開発とツールのブログ投稿では、Visual Studio [Web アクセシビリティ チェッカーについて説明します](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.WebAccessibilityChecker)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-212">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.WebAccessibilityChecker).</span></span>  <span data-ttu-id="98d0c-213">詳細については、「アクセス可能な Web サイトの構築」に移動 [すると、はるかに簡単になりました](https://devblogs.microsoft.com/aspnet/building-accessible-websites-just-got-a-lot-easier)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-213">For more information, navigate to [Building accessible websites just got a lot easier](https://devblogs.microsoft.com/aspnet/building-accessible-websites-just-got-a-lot-easier).</span></span>  

#### <a name="core-accessibility-api-mappings-11"></a><span data-ttu-id="98d0c-214">コア アクセシビリティ API マッピング 1.1</span><span class="sxs-lookup"><span data-stu-id="98d0c-214">Core Accessibility API Mappings 1.1</span></span>  

<span data-ttu-id="98d0c-215">この W3C マッピング ドキュメントでは、Web コンテンツ言語のセマンティクスがアクセシビリティ API に公開される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-215">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  <span data-ttu-id="98d0c-216">詳細については、「Core [Accessibility API Mappings 1.1」に移動します](https://www.w3.org/TR/core-aam-1.1)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-216">For more information, navigate to [Core Accessibility API Mappings 1.1](https://www.w3.org/TR/core-aam-1.1).</span></span>  

#### <a name="easy-checks--a-first-review-of-web-accessibility"></a><span data-ttu-id="98d0c-217">簡単なチェック – Web アクセシビリティの最初のレビュー</span><span class="sxs-lookup"><span data-stu-id="98d0c-217">Easy Checks – A First Review of Web Accessibility</span></span>  

<span data-ttu-id="98d0c-218">WEB ページのアクセシビリティの向上に役立つ一連のクイック チェックが、WAI によって行います。</span><span class="sxs-lookup"><span data-stu-id="98d0c-218">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>  <span data-ttu-id="98d0c-219">詳細については、「簡単なチェック [- Web アクセシビリティの最初のレビュー」に移動します](https://www.w3.org/WAI/eval/preliminary.html)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-219">For more information, navigate to [Easy Checks – A First Review of Web Accessibility](https://www.w3.org/WAI/eval/preliminary.html).</span></span>  

#### <a name="how-to-meet-wcag-20"></a><span data-ttu-id="98d0c-220">WCAG 2.0 を満たす方法</span><span class="sxs-lookup"><span data-stu-id="98d0c-220">How to Meet WCAG 2.0</span></span>  

<span data-ttu-id="98d0c-221">Web コンテンツ アクセシビリティ ガイドライン \(WCAG\) 2.0 の要件 \(成功基準\) とテクニックに関するクイック リファレンス。</span><span class="sxs-lookup"><span data-stu-id="98d0c-221">A quick reference to Web Content Accessibility Guidelines \(WCAG\) 2.0 requirements \(success criteria\) and techniques.</span></span>  <span data-ttu-id="98d0c-222">詳細については [、「WCAG 2.0 を満たす方法」に移動します](https://www.w3.org/WAI/WCAG20/quickref)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-222">For more information, navigate to [How to Meet WCAG 2.0](https://www.w3.org/WAI/WCAG20/quickref).</span></span>  

#### <a name="html-accessibility-api-mappings-10"></a><span data-ttu-id="98d0c-223">HTML アクセシビリティ API マッピング 1.0</span><span class="sxs-lookup"><span data-stu-id="98d0c-223">HTML Accessibility API Mappings 1.0</span></span>  

<span data-ttu-id="98d0c-224">この W3C マッピング ドキュメントでは、HTML5.1 要素と属性がプラットフォームアクセシビリティ API にマップされる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-224">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>  <span data-ttu-id="98d0c-225">詳細については [、「HTML アクセシビリティ API マッピング 1.0」に移動します](https://www.w3.org/TR/html-aam-1.0)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-225">For more information, navigate to [HTML Accessibility API Mappings 1.0](https://www.w3.org/TR/html-aam-1.0).</span></span>  

#### <a name="quick-tips"></a><span data-ttu-id="98d0c-226">クイック ヒント</span><span class="sxs-lookup"><span data-stu-id="98d0c-226">Quick Tips</span></span>

<span data-ttu-id="98d0c-227">[A11Y](http://a11yproject.com)のアクセシビリティに関するクイック Web 開発のヒントのProject。</span><span class="sxs-lookup"><span data-stu-id="98d0c-227">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com).</span></span>  <span data-ttu-id="98d0c-228">詳細については、「クイック メニュー」[に移動ヒント。](http://a11yproject.com#Quick-tips)</span><span class="sxs-lookup"><span data-stu-id="98d0c-228">For more information, navigate to [Quick Tips](http://a11yproject.com#Quick-tips).</span></span>  

#### <a name="site-scan"></a><span data-ttu-id="98d0c-229">サイト スキャン</span><span class="sxs-lookup"><span data-stu-id="98d0c-229">Site Scan</span></span>  

<span data-ttu-id="98d0c-230">サイト センターのサイト Microsoft Edge Dev ツールは、古いライブラリ、レイアウトの問題、アクセシビリティの問題をチェックします。</span><span class="sxs-lookup"><span data-stu-id="98d0c-230">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>  <span data-ttu-id="98d0c-231">詳細については、「サイト スキャン」 [に移動します](https://developer.microsoft.com/microsoft-edge/tools)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-231">For more information, navigate to [Site Scan](https://developer.microsoft.com/microsoft-edge/tools).</span></span>  

#### <a name="techniques-for-wcag-20"></a><span data-ttu-id="98d0c-232">WCAG 2.0 の手法</span><span class="sxs-lookup"><span data-stu-id="98d0c-232">Techniques for WCAG 2.0</span></span>  

<span data-ttu-id="98d0c-233">Web コンテンツ アクセシビリティ ガイドライン [(WCAG) 2.0](https://w3.org/TR/WCAG20) の成功基準を満たす Web 開発者向けのガイダンスを提供する W3C の手法。</span><span class="sxs-lookup"><span data-stu-id="98d0c-233">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20) success criteria.</span></span>  <span data-ttu-id="98d0c-234">詳細については [、「WCAG 2.0 のテクニック」に移動します](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-234">For more information, navigate to [Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/Overview.html).</span></span>  

#### <a name="tips-on-developing-for-web-accessibility"></a><span data-ttu-id="98d0c-235">ヒントアクセシビリティの開発に関するページ</span><span class="sxs-lookup"><span data-stu-id="98d0c-235">Tips on Developing for Web Accessibility</span></span>  

<span data-ttu-id="98d0c-236">ヒント障がい者がアクセスしやすい Web コンテンツの開発について W3C から説明します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-236">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>  <span data-ttu-id="98d0c-237">詳細については、「Web アクセシビリティの[開発ヒント」に移動します](https://w3.org/WAI/gettingstarted/tips/developing.html)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-237">For more information, navigate to [Tips on Developing for Web Accessibility](https://w3.org/WAI/gettingstarted/tips/developing.html).</span></span>  

#### <a name="wai-aria-authoring-practices-11"></a><span data-ttu-id="98d0c-238">WAI-ARIA オーサリング プラクティス 1.1</span><span class="sxs-lookup"><span data-stu-id="98d0c-238">WAI-ARIA Authoring Practices 1.1</span></span>  

<span data-ttu-id="98d0c-239">W3C のドキュメントで、読者は、WAI-ARIA 1.1 の使い方を理解し、WAI-ARIA の役割、状態、およびプロパティを使用してウィジェット、ナビゲーション、および動作をアクセス可能にする方法を推奨します。</span><span class="sxs-lookup"><span data-stu-id="98d0c-239">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>  <span data-ttu-id="98d0c-240">詳細については [、「WAI-ARIA オーサリング プラクティス 1.1」に移動します](http://w3c.github.io/aria-practices)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-240">For more information, navigate to [WAI-ARIA Authoring Practices 1.1](http://w3c.github.io/aria-practices).</span></span>  

#### <a name="wai-guidelines-and-techniques"></a><span data-ttu-id="98d0c-241">WAI のガイドラインとテクニック</span><span class="sxs-lookup"><span data-stu-id="98d0c-241">WAI Guidelines and Techniques</span></span>  

<span data-ttu-id="98d0c-242">WAI によって開発された一連の Web アクセシビリティ ガイドラインと標準。</span><span class="sxs-lookup"><span data-stu-id="98d0c-242">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  <span data-ttu-id="98d0c-243">詳細については、「WAI ガイドラインと [テクニック」に移動します](https://w3.org/WAI/guid-tech.html)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-243">For more information, navigate to [WAI Guidelines and Techniques](https://w3.org/WAI/guid-tech.html).</span></span>  

#### <a name="web-accessibility-evaluation-tools-list"></a><span data-ttu-id="98d0c-244">Web アクセシビリティ評価ツールの一覧</span><span class="sxs-lookup"><span data-stu-id="98d0c-244">Web Accessibility Evaluation Tools List</span></span>  

<span data-ttu-id="98d0c-245">Web サイトがアクセシビリティ ガイドラインを満たしているかどうかを判断するための Web アクセシビリティ評価ツールの一覧。</span><span class="sxs-lookup"><span data-stu-id="98d0c-245">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>  <span data-ttu-id="98d0c-246">詳細については、「Web アクセシビリティ評価 [ツールの一覧」に移動します](https://www.w3.org/WAI/ER/tools/index.html)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-246">For more information, navigate to [Web Accessibility Evaluation Tools List](https://www.w3.org/WAI/ER/tools/index.html).</span></span>  

#### <a name="web-accessibility-perspectives-explore-the-impact-and-benefits-for-everyone"></a><span data-ttu-id="98d0c-247">Web アクセシビリティの観点: すべてのユーザーに対する影響と利点を確認する</span><span class="sxs-lookup"><span data-stu-id="98d0c-247">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>  

<span data-ttu-id="98d0c-248">アクセシビリティの影響とすべてのユーザーにとっての利点に関する W3C による一連の短い状況ビデオ。</span><span class="sxs-lookup"><span data-stu-id="98d0c-248">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>  <span data-ttu-id="98d0c-249">詳細については、「Web アクセシビリティの観点: すべてのユーザーに対する影響と [利点を確認する」に移動します](https://w3.org/WAI/perspectives)。</span><span class="sxs-lookup"><span data-stu-id="98d0c-249">For more information, navigate to [Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone](https://w3.org/WAI/perspectives).</span></span>  

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "仮想マシン |Microsoft Edge開発者"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 "ガイドの完全なナレーター |Microsoft サポート"  
[MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]: https://support.microsoft.com/windows/414948ba-8b1c-d3bd-8615-0e5e32204198 "拡大鏡を使用して、画面の表示を簡単に行|Microsoft サポート"  

[AccessibilityinsightsWebOverview]: https://accessibilityinsights.io/docs/web/overview "Web サービスのアクセシビリティ|アクセシビリティインサイト"  

[AndroidDeveloperDevicesManagingAvdsHtml]: https://developer.android.com/tools/devices/managing-avds.html "仮想デバイスの作成と管理|Android 開発者"  
[AndroidDeveloperDevicesEmulatorHtml]: https://developer.android.com/tools/devices/emulator.html "Android エミュレーター でアプリを実行|Android 開発者"  
[AndroidDeveloperSdkInstallingStudioHtml]: https://developer.android.com/sdk/installing/studio.html "Android Studio のダウンロード |Android 開発者"  

[AppleAccessibilityMacVision]: https://www.apple.com/accessibility/mac/vision "Vision アクセシビリティ - Mac |Apple"  

[AssistivlabsMain]: https://assistivlabs.com "Assistiv Labs"  

[FreedomscientificSoftwareJaws]: https://www.freedomscientific.com/products/software/jaws "JAWS® |Freedom Scientific"  
[FreedomscientificSoftwareZoomtext]: https://www.freedomscientific.com/products/software/zoomtext "ZoomText |Freedom Scientific"  

[GooglePlayStoreAndroidAccessibilitySuite]: https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback "Android アクセシビリティ スイート |GooglePlay ストア"  

[NvaccessAboutNvda]: https://www.nvaccess.org/about-nvda "NVDA |NV Access"  

[W3cPerspectiveVideosKeyboard]: https://www.w3.org/WAI/perspective-videos/keyboard "キーボードの互換性|W3C"  

[WebaimProjectsLowvisionsurvey2]: https://webaim.org/projects/lowvisionsurvey2 "低ビジョンのユーザーのアンケート \#2結果|WebAIM"  
[WebaimProjectsScreenreadersurvey8]: https://webaim.org/projects/screenreadersurvey8 "スクリーン リーダー ユーザーアンケート \#8 結果|WebAIM"  
[WebaimArticlesScreenreaderTesting]: https://webaim.org/articles/screenreader_testing "スクリーン リーダーを使用したテスト|WebAIM"  
