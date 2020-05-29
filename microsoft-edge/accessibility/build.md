---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: ベストプラクティスとアクセシビリティの高いリッチインターネットアプリケーション (ARIA) を組み合わせて、アクセシビリティ対応の web サイトを作成する方法について説明します。
title: アクセシビリティ-ビルド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセシビリティ対応の web サイト、edge、web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 4412fef6bb78b5a393ccafd5a2cfa79aba223141
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568812"
---
# <span data-ttu-id="d7fc3-104">アクセシビリティの高い Web サイトを構築する</span><span class="sxs-lookup"><span data-stu-id="d7fc3-104">Building Accessible Websites</span></span>
<span data-ttu-id="d7fc3-105">Web には、HTML、CSS、JavaScript の組み合わせを使って構築された動的で複雑な web サイト、アプリケーション、ユーザーインターフェイスが埋め込まれています。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="d7fc3-106">ただし、アクセシビリティを考慮せずに設計および構築すると、[支援技術](https://webaim.org/articles/motor/assistive)を利用して web を参照するユーザーは、これらの複雑な web サイトを使用することが困難になります。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span> <span data-ttu-id="d7fc3-107">障碍のあるユーザーが使いやすい web サイトを構築するには、ユーザーインターフェイスに関するセマンティクス情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span> <span data-ttu-id="d7fc3-108">これにより、スクリーンリーダーなどの支援技術によって必要な情報を伝えることができるので、web サイトを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>

<span data-ttu-id="d7fc3-109">Microsoft Edge でサポートされている新しい HTML5 機能 accessibly については、 [HTML5Accessibility](https://html5accessibility.com)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

## <span data-ttu-id="d7fc3-110">アクセシビリティのしくみ</span><span class="sxs-lookup"><span data-stu-id="d7fc3-110">How Accessibility Works</span></span>

<span data-ttu-id="d7fc3-111">支援技術により、コンピューターに通常ない機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-111">Assistive technologies add capabilities that computers don't usually have.</span></span> <span data-ttu-id="d7fc3-112">たとえば、視覚障碍のあるユーザーは、マウスと画面でブラウザーを直接使用するのではなく、スクリーンリーダーなどの支援技術と組み合わせてキーボードを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span> <span data-ttu-id="d7fc3-113">Microsoft プラットフォームと web 上のアプリケーションの場合、支援技術は microsoft [UI オートメーション](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、microsoft Edge のドキュメントオブジェクトモデル (DOM)、またはこれらの組み合わせなどのアプリケーション固有のオブジェクトモデルと連携します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx), an application-specific object model such as the Document Object Model (DOM) in Microsoft Edge, or a combination of these.</span></span>

<span data-ttu-id="d7fc3-114">Web 開発者の場合は、特定の HTML 要素が UI オートメーションオブジェクトに対応しているため、これらの HTML 要素を選択するときに、開発者はこれらの要素に組み込まれているアクセシビリティプロパティとイベントを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span> <span data-ttu-id="d7fc3-115">通常、web サイトを作成しているときに、アプリがアクセスできるように、API が正しく書き込まれている (または適切な要素が指定されている) ことを確認するだけで十分です。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to (or that the appropriate element is specified), in order for the application to be accessible.</span></span> <span data-ttu-id="d7fc3-116">詳細については[、「Microsoft Edge で ARIA と UI オートメーション](./build/ARIA-and-UI-Automation.md)を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-116">Check out [ARIA and UI Automation in Microsoft Edge](./build/ARIA-and-UI-Automation.md) for more information.</span></span>  <span data-ttu-id="d7fc3-117">アクセシビリティの高いユニバーサル Windows プラットフォーム (UWP) アプリの詳細については、Windows デベロッパーセンターの[アクセシビリティ](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-117">For information on accessible Universal Windows Platform (UWP) apps, see the [Accessibility](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) topic in the Windows Dev Center.</span></span>

<span data-ttu-id="d7fc3-118">動的コンテンツに関する多くの一般的なアクセシビリティの問題については、適切なコーディングの方法で対処できます。 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629)ドキュメントには、よりアクセシビリティの高い動的 web アプリケーションを作成するのに役立つ多くの手法とベストプラクティスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span> <span data-ttu-id="d7fc3-119">ただし、適切にコードが記述されている場合でも、動的コンテンツは必ずしもアクセス可能であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span> <span data-ttu-id="d7fc3-120">アクセシビリティに対応した[リッチインターネットアプリケーション (ARIA)](#aria)は、この問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="d7fc3-121">Web アクセシビリティの詳細については、「web アクセシビリティ[イニシアチブ](https://www.w3.org/WAI/)(wai-aria 使った) による[Web アクセシビリティの概要](https://www.w3.org/WAI/intro/accessibility.php)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative](https://www.w3.org/WAI/) (WAI).</span></span>

## <span data-ttu-id="d7fc3-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="d7fc3-122">ARIA</span></span>
<span data-ttu-id="d7fc3-123">W3C's [Web Accessibility イニシアチブ](https://www.w3.org/WAI/)によるアクセシビリティ性の高い[リッチインターネットアプリケーション](https://www.w3.org/TR/wai-aria/)(ARIA) の仕様は、動的な Web コンテンツとカスタムユーザーインターフェイスをすべてのユーザーがアクセスできるようにする構文として定義されています。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-123">The [Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI/) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span> <span data-ttu-id="d7fc3-124">ARIA は、カスタムセマンティクスを伝えるために設計された追加の属性 (ロール、プロパティ、状態) を使って HTML を拡張します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-124">ARIA extends HTML by using additional attributes (roles, properties, and states) that are designed to convey custom semantics.</span></span> <span data-ttu-id="d7fc3-125">これらの属性は、ブラウザーでコントロールの状態と役割をアクセシビリティ API に渡すために使われます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>

### <span data-ttu-id="d7fc3-126">役割、プロパティ、状態</span><span class="sxs-lookup"><span data-stu-id="d7fc3-126">Roles, Properties, and States</span></span>
<span data-ttu-id="d7fc3-127">ARIA ロールは、属性を使用して要素に対して設定され、 [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) 要素に関する支援技術とアクセシビリティ api 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-127">ARIA roles are set on elements using the [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) attribute to give assistive technologies and accessibility APIs information about the element.</span></span> <span data-ttu-id="d7fc3-128">たとえば、次の `<li>` 要素は、 `role="menuitem"` メニュー内の項目であることを示すために割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>

``` html
<li role="menuitem">Home</li>
```

<span data-ttu-id="d7fc3-129">ARIA の状態とプロパティは、ロールの特性の定義を形成するために、オブジェクトに関する特定の情報を提供する aria のプレフィックス付き属性です。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span> <span data-ttu-id="d7fc3-130">プロパティは、やなどのオブジェクトの性質にとって重要な属性です [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-130">Properties are attributes that are essential to the nature of an object, like [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) and [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx).</span></span> <span data-ttu-id="d7fc3-131">プロパティの変更は、オブジェクトの意味に影響します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-131">Changing a property affects the meaning of the object.</span></span> <span data-ttu-id="d7fc3-132">次の例では、メニュー項目にプロパティを設定して、ポップアップがあることを示してい `aria-haspopup="true"` `<li>` ます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>

``` html
<li role="menuitem" aria-haspopup="true">Open</li>
```

<span data-ttu-id="d7fc3-133">状態はオブジェクトの性質を変更しませんが、またはなどのオブジェクトに関連付けられたオブジェクトまたはユーザーの操作に関連する情報を表し [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) ます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) or [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx).</span></span> <span data-ttu-id="d7fc3-134">たとえば、次の例に示す状態は、 `aria-checked="false"` チェックボックスがオフになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>

``` html
<div role="checkbox" aria-checked="false">Accept</div>
```

<span data-ttu-id="d7fc3-135">すべての役割、プロパティ、状態の一覧を表示するには、W3C による[役割モデル](https://www.w3.org/TR/wai-aria-1.1/#roles)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1/#roles) by the W3C to see a full list of roles, properties, and states.</span></span>

<span data-ttu-id="d7fc3-136">ARIA の詳細については、「[リソース](#resources)」セクションの「aria」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-136">For more information on ARIA, see the ARIA in the [Resources](#resources) section.</span></span>

## <span data-ttu-id="d7fc3-137">リソース</span><span class="sxs-lookup"><span data-stu-id="d7fc3-137">Resources</span></span>

### <span data-ttu-id="d7fc3-138">アクセシビリティの基本</span><span class="sxs-lookup"><span data-stu-id="d7fc3-138">Accessibility Basics</span></span>
#### [<span data-ttu-id="d7fc3-139">A11Y プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d7fc3-139">The A11Y Project</span></span>](http://a11yproject.com/)
<span data-ttu-id="d7fc3-140">A11Y プロジェクトは、web アクセシビリティを容易にするための、コミュニティ主導の作業です。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-140">The A11Y Project is a community-driven effort to make web accessibility easier.</span></span> <span data-ttu-id="d7fc3-141">[A11Y プロジェクト](https://a11yproject.com/)サイトでは、基本的なアクセシビリティの原則、アクセシビリティ対応のパターンとウィジェット[ライブラリ](https://a11yproject.com/patterns)、アクセシビリティソフトウェア、ブログ、書籍、ツールに関する[リソース](http://a11yproject.com/resources.html)について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-141">Check out [The A11Y Project](https://a11yproject.com/) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>

#### [<span data-ttu-id="d7fc3-142">Web アクセシビリティイニシアチブ (WAI-ARIA 使った)</span><span class="sxs-lookup"><span data-stu-id="d7fc3-142">Web Accessibility Initiative (WAI)</span></span>](https://w3.org/WAI/)
<span data-ttu-id="d7fc3-143">W3C's Web Accessibility イニシアチブ (WAI-ARIA 使った) は、web のアクセシビリティを向上させるための取り組みです。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-143">The W3C's Web Accessibility Initiative (WAI) is an effort to help improve the accessibility of the web.</span></span> <span data-ttu-id="d7fc3-144">[Web アクセシビリティの使用を開始](https://www.w3.org/WAI/gettingstarted/Overview.html)するためのさまざまなリソースが用意されており、それを対象とした[デザイン](https://www.w3.org/WAI/users/Overview.html)、[チュートリアル、プレゼンテーション](https://www.w3.org/WAI/train.html)などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-144">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>

### <span data-ttu-id="d7fc3-145">アクセシビリティのブログ</span><span class="sxs-lookup"><span data-stu-id="d7fc3-145">Accessibility Blogs</span></span>
#### [<span data-ttu-id="d7fc3-146">Paciello グループ</span><span class="sxs-lookup"><span data-stu-id="d7fc3-146">The Paciello Group</span></span>](https://www.paciellogroup.com/blog/)
<span data-ttu-id="d7fc3-147">Paciello グループは、世界中の組織に対してコンサルティングと技術のソリューションを提供します。顧客がすべての対象ユーザーに対して効率的かつ効率的に連絡を取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-147">The Paciello Group provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span> <span data-ttu-id="d7fc3-148">Web アクセシビリティのベストプラクティス、アクセシビリティツール、アクセシビリティの傾向などのトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-148">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>

#### [<span data-ttu-id="d7fc3-149">簡単にアクセス</span><span class="sxs-lookup"><span data-stu-id="d7fc3-149">Simply Accessible</span></span>](http://simplyaccessible.com/articles/)
<span data-ttu-id="d7fc3-150">アクセシビリティのトレーニング、コンサルティングなど、web 上のアクセシビリティの認識を向上させるアクセシビリティスペシャリストのチームであるということができます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-150">Simply Accessible is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span> <span data-ttu-id="d7fc3-151">この[セクションでは、web](http://simplyaccessible.com/articles/)アクセシビリティ、アクセシビリティの高いデザインに関するベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-151">Their [Articles](http://simplyaccessible.com/articles/) section discusses best practices for web accessibility, accessible design, and more.</span></span>

#### [<span data-ttu-id="d7fc3-152">SSB BART グループ (SSB)</span><span class="sxs-lookup"><span data-stu-id="d7fc3-152">SSB BART Group (SSB)</span></span>](http://www.ssbbartgroup.com/blog/)
<span data-ttu-id="d7fc3-153">SSB BART グループは、アクセシビリティ対応の製品とサービスの開発と展開において、クライアントをサポートするデジタルアクセシビリティ企業です。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-153">SSB BART Group is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span> <span data-ttu-id="d7fc3-154">これらのブログは、ARIA のベストプラクティス、アクセシビリティの傾向、ウェビナーなどのトピックに対応しています。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-154">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>

### <span data-ttu-id="d7fc3-155">アクセシビリティの高い例</span><span class="sxs-lookup"><span data-stu-id="d7fc3-155">Accessible Examples</span></span>
#### [<span data-ttu-id="d7fc3-156">同盟: チュートリアル</span><span class="sxs-lookup"><span data-stu-id="d7fc3-156">ally.js - Tutorials</span></span>](http://allyjs.io/tutorials/)
<span data-ttu-id="d7fc3-157">アクセシビリティをより簡単にするために、アクセシビリティに関する問題を解決するための JavaScript ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-157">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>

#### [<span data-ttu-id="d7fc3-158">Heydonworks-ARIA の例</span><span class="sxs-lookup"><span data-stu-id="d7fc3-158">Heydonworks - ARIA Examples</span></span>](http://heydonworks.com/practical_aria_examples/)
<span data-ttu-id="d7fc3-159">アプリケーションのアクセシビリティを向上させるための実用的な ARIA の例</span><span class="sxs-lookup"><span data-stu-id="d7fc3-159">Practical ARIA examples to enhance your application accessibility</span></span>

#### [<span data-ttu-id="d7fc3-160">OpenAjax の例</span><span class="sxs-lookup"><span data-stu-id="d7fc3-160">OpenAjax Examples</span></span>](http://oaa-accessibility.org/)
<span data-ttu-id="d7fc3-161">OpenAjax アライアンス web サイトは、WAI-ARIA 使ったの規則を確認するための優れたリソースであり、WAI-ARIA 使ったのいくつかの実装の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-161">The OpenAjax Alliance website is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>

#### [<span data-ttu-id="d7fc3-162">傾向</span><span class="sxs-lookup"><span data-stu-id="d7fc3-162">Patterns</span></span>](http://a11yproject.com/patterns.html)
<span data-ttu-id="d7fc3-163">[A11Y プロジェクトに](http://a11yproject.com/)は、メニュー、ボタン、ヒントなど、アクセシビリティ対応のウィジェットとパターンのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-163">[The A11Y Project](http://a11yproject.com/) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>

### <span data-ttu-id="d7fc3-164">ユーザー補助の手法 & ツール</span><span class="sxs-lookup"><span data-stu-id="d7fc3-164">Accessibility Techniques & Tools</span></span>
#### [<span data-ttu-id="d7fc3-165">アクセシビリティ: Microsoft Edge のアクセシビリティ対応の拡張機能を作成する</span><span class="sxs-lookup"><span data-stu-id="d7fc3-165">Accessibility: Creating accessible extension icons for Microsoft Edge</span></span>](../extensions/guides/accessibility.md)
<span data-ttu-id="d7fc3-166">Microsoft Edge のアクセシビリティ対応の拡張機能の作成に関するガイダンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-166">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>

#### [<span data-ttu-id="d7fc3-167">アクセシビリティ対応の名前と説明: 計算とマッピング1.1</span><span class="sxs-lookup"><span data-stu-id="d7fc3-167">Accessible Name and Description: Computation and Mappings 1.1</span></span>](https://www.w3.org/TR/accname-1.1/)
<span data-ttu-id="d7fc3-168">この W3C マッピングドキュメントでは、ブラウザーが web コンテンツ言語からアクセシビリティの高いオブジェクトの名前と説明を特定し、アクセシビリティ Api でそれらを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-168">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>

#### [<span data-ttu-id="d7fc3-169">アクセシビリティ評価リソース</span><span class="sxs-lookup"><span data-stu-id="d7fc3-169">Accessibility Evaluation Resources</span></span>](https://www.w3.org/WAI/eval/Overview.html)
<span data-ttu-id="d7fc3-170">アクセシビリティ評価リソースは、アクセシビリティのために web サイトを評価するためのさまざまな方法を示す W3C のマルチページリソースです。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-170">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>

#### [<span data-ttu-id="d7fc3-171">支援技術の互換性テスト</span><span class="sxs-lookup"><span data-stu-id="d7fc3-171">Assistive technology compatibility tests</span></span>](http://www.powermapper.com/tests/)
<span data-ttu-id="d7fc3-172">スクリーンリーダーのように、さまざまなコンテンツの種類や標準が支援技術 (AT) でどのように動作するかを示すテスト結果。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-172">Test results showing how different content types and standards behave in assistive technologies (AT) like screen readers.</span></span>

#### [<span data-ttu-id="d7fc3-173">アクセシビリティの高い web サイトを作成するのがとても簡単に</span><span class="sxs-lookup"><span data-stu-id="d7fc3-173">Building accessible websites just got a lot easier</span></span>](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)
<span data-ttu-id="d7fc3-174">この .NET Web 開発とツールのブログ投稿では、Visual Studio 拡張機能の[Web アクセシビリティチェック](https://go.microsoft.com/fwlink/p/?linkid=841539)について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-174">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://go.microsoft.com/fwlink/p/?linkid=841539).</span></span>

#### [<span data-ttu-id="d7fc3-175">Core Accessibility API マッピング1.1</span><span class="sxs-lookup"><span data-stu-id="d7fc3-175">Core Accessibility API Mappings 1.1</span></span>](https://www.w3.org/TR/core-aam-1.1/)
<span data-ttu-id="d7fc3-176">この W3C マッピングドキュメントでは、web コンテンツ言語がアクセシビリティ Api にどのように公開されるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-176">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  

#### [<span data-ttu-id="d7fc3-177">簡単なチェック– Web アクセシビリティの最初のレビュー</span><span class="sxs-lookup"><span data-stu-id="d7fc3-177">Easy Checks – A First Review of Web Accessibility</span></span>](https://www.w3.org/WAI/eval/preliminary.html)
<span data-ttu-id="d7fc3-178">WAI-ARIA 使ったによって、web ページのアクセシビリティを向上させるための一連のクイックチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-178">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>

#### [<span data-ttu-id="d7fc3-179">WCAG 2.0 の対応方法</span><span class="sxs-lookup"><span data-stu-id="d7fc3-179">How to Meet WCAG 2.0</span></span>](https://www.w3.org/WAI/WCAG20/quickref/)
<span data-ttu-id="d7fc3-180">Web コンテンツのアクセシビリティガイドライン (WCAG) 2.0 の要件 (成功の条件) と手法のクイックリファレンス。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-180">A quick reference to Web Content Accessibility Guidelines (WCAG) 2.0 requirements (success criteria) and techniques.</span></span>

#### [<span data-ttu-id="d7fc3-181">HTML アクセシビリティ API マッピング1.0</span><span class="sxs-lookup"><span data-stu-id="d7fc3-181">HTML Accessibility API Mappings 1.0</span></span>](https://www.w3.org/TR/html-aam-1.0/)
<span data-ttu-id="d7fc3-182">この W3C マッピングドキュメントでは、HTML 5.1 の要素と属性が platform accessibility Api にどのように対応するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-182">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>


#### [<span data-ttu-id="d7fc3-183">ポップヒント</span><span class="sxs-lookup"><span data-stu-id="d7fc3-183">Quick Tips</span></span>](http://a11yproject.com/#Quick-tips)
<span data-ttu-id="d7fc3-184">[A11Y プロジェクト](http://a11yproject.com/)でのアクセシビリティに関する web 開発のクイックヒントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-184">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com/).</span></span>

#### [<span data-ttu-id="d7fc3-185">サイトのスキャン</span><span class="sxs-lookup"><span data-stu-id="d7fc3-185">Site Scan</span></span>](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)
<span data-ttu-id="d7fc3-186">Microsoft Edge デベロッパーセンターのサイトスキャンツールは、古いライブラリ、レイアウトの問題、アクセシビリティの問題をチェックします。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-186">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>

#### [<span data-ttu-id="d7fc3-187">WCAG 2.0 の手法</span><span class="sxs-lookup"><span data-stu-id="d7fc3-187">Techniques for WCAG 2.0</span></span>](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)
<span data-ttu-id="d7fc3-188">会議[Web コンテンツのアクセシビリティガイドライン (WCAG) 2.0](https://w3.org/TR/WCAG20/)の成功条件について web 開発者向けのガイダンスを提供する W3C の手法。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-188">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20/) success criteria.</span></span>

#### [<span data-ttu-id="d7fc3-189">Web アクセシビリティの開発に関するヒント</span><span class="sxs-lookup"><span data-stu-id="d7fc3-189">Tips on Developing for Web Accessibility</span></span>](https://w3.org/WAI/gettingstarted/tips/developing.html)
<span data-ttu-id="d7fc3-190">障碍のある方にとって使いやすい web コンテンツの開発に関する W3C のヒント。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-190">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>

#### [<span data-ttu-id="d7fc3-191">WAI-ARIA 使った-ARIA のオーサリングプラクティス1.1</span><span class="sxs-lookup"><span data-stu-id="d7fc3-191">WAI-ARIA Authoring Practices 1.1</span></span>](http://w3c.github.io/aria-practices/)
<span data-ttu-id="d7fc3-192">WAI-ARIA 使った-ARIA 1.1 の使用方法を理解し、WAI-ARIA 使った-ARIA の役割、状態、プロパティを使ってアクセスできるウィジェット、ナビゲーション、動作を実現するためのアプローチを提供する、W3C によるドキュメント。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-192">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>

#### [<span data-ttu-id="d7fc3-193">WAI-ARIA 使ったのガイドラインと手法</span><span class="sxs-lookup"><span data-stu-id="d7fc3-193">WAI Guidelines and Techniques</span></span>](https://w3.org/WAI/guid-tech.html)
<span data-ttu-id="d7fc3-194">WAI-ARIA 使ったによって開発された一連の web アクセシビリティガイドラインと標準。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-194">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  

#### [<span data-ttu-id="d7fc3-195">Web アクセシビリティ評価ツールの一覧</span><span class="sxs-lookup"><span data-stu-id="d7fc3-195">Web Accessibility Evaluation Tools List</span></span>](https://www.w3.org/WAI/ER/tools/index.html)
<span data-ttu-id="d7fc3-196">Web サイトがアクセシビリティガイドラインを満たしているかどうかを判断するのに役立つ web アクセシビリティ評価ツールの一覧です。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-196">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>

#### [<span data-ttu-id="d7fc3-197">Web アクセシビリティの観点: すべてのユーザーに対する影響と利点を調べる</span><span class="sxs-lookup"><span data-stu-id="d7fc3-197">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>](https://w3.org/WAI/perspectives/)
<span data-ttu-id="d7fc3-198">アクセシビリティの影響とすべてのユーザーの利点について、W3C による一連の短いビデオ。</span><span class="sxs-lookup"><span data-stu-id="d7fc3-198">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>
