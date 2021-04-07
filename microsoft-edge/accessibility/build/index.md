---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: ベスト プラクティスと Accessible Rich Internet Applications (ARIA) を組み合わせて、アクセス可能な Web サイトを作成する方法について説明します。
title: ビルド |アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 3bc16450a3a64c06d290d1d3e112a9b2faecbe14
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480154"
---
# <a name="building-accessible-websites"></a>アクセス可能な Web サイトの構築

Web には、HTML、CSS、JavaScript の組み合わせを使用して構築された動的で複雑な Web サイト、アプリケーション、およびユーザー インターフェイスが埋め込みされています。  ただし、アクセシビリティを念頭に置いて設計および構築した場合、これらの複雑な Web サイトは、支援[](https://webaim.org/articles/motor/assistive)テクノロジを使用して Web を閲覧するユーザーが使用することは困難です。 障がい者がアクセスできる Web サイトを構築するには、ユーザー インターフェイスに関するセマンティックな情報が必要です。 これにより、スクリーン リーダーなどの支援テクノロジは、さまざまな機能を持つユーザーが Web サイトを使用するのに役立つ必要な情報を伝えます。

Microsoft Edge でサポートされている新しい HTML5 機能の詳細については [、「HTML5Accessibility」](https://html5accessibility.com) を参照してください。

## <a name="how-accessibility-works"></a>アクセシビリティのしくみ

支援テクノロジは、通常はコンピューターにはない機能を追加します。 たとえば、視覚障害のあるユーザーは、マウスと画面でブラウザーを直接使用するのではなく、スクリーン リーダーなどの支援テクノロジと組み合わせてキーボードを使用できます。 Microsoft プラットフォーム上および Web 上のアプリケーションの場合、支援テクノロジは Microsoft [UI オートメーション](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、Microsoft Edge のドキュメント オブジェクト モデル (DOM) などのアプリケーション固有のオブジェクト モデル、またはこれらの組み合わせと対話します。

Web 開発者の場合、特定の HTML 要素は UI オートメーション オブジェクトにマップされます。そのため、これらの HTML 要素を選択する場合、開発者はそれらの要素に組み込みのアクセシビリティ プロパティとイベントを使用できます。 Web サイトを開発する場合、アプリケーションにアクセスするには、通常、API が正しく書き込まれる (または適切な要素が指定されていることを) 確認する必要があります。 詳細については [、Microsoft Edge の ARIA と UI オートメーション](./ARIA-and-UI-Automation.md) を参照してください。  アクセス可能なユニバーサル Windows プラットフォーム (UWP) アプリの詳細[](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)については、Windows デベロッパー センターの 「アクセシビリティ」トピックに移動します。

動的コンテンツに関する多くの一般的なアクセシビリティの問題は、適切なコーディング方法によって解決できます。 [また、WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) のドキュメントには、よりアクセスしやすい動的 Web アプリケーションを作成するための多くの手法とベスト プラクティスが含まれています。 ただし、適切にコード化された場合でも、動的コンテンツにアクセスできるとは限りません。 [アクセス可能なリッチ インターネット アプリケーション (ARIA) は、この](#aria) 問題を解決するのに役立ちます。  

Web アクセシビリティの詳細については、「Web アクセシビリティ[](https://www.w3.org/WAI/intro/accessibility.php)イニシアティブ (WAI) による Web アクセシビリティの概要[」を参照してください](https://www.w3.org/WAI)。

## <a name="aria"></a>ARIA

W3C の Web アクセシビリティ イニシアティブによるアクセシビリティ対応リッチ インターネット[](https://www.w3.org/WAI/)アプリケーション[](https://www.w3.org/TR/wai-aria/) (ARIA) 仕様は、動的 Web コンテンツとカスタム ユーザー インターフェイスをすべてのユーザーがアクセス可能にするための構文として定義されています。 ARIA は、カスタム セマンティクスを伝えるために設計された追加の属性 (ロール、プロパティ、および状態) を使用して HTML を拡張します。 これらの属性は、ブラウザーがコントロールの状態と役割をアクセシビリティ API に渡す場合に使用されます。

### <a name="roles-properties-and-states"></a>ロール、プロパティ、および状態

ARIA の役割は、属性を使用して要素に関する支援テクノロジとアクセシビリティ API 情報を提供するために要素 [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) に設定されます。 たとえば、メニュー内のアイテムを示す次の要素が割 `<li>` `role="menuitem"` り当てられます。

```html
<li role="menuitem">Home</li>
```

ARIA の状態とプロパティは、ロールの性質の定義を形成するのに役立つオブジェクトに関する特定の情報を提供する、aria プレフィックス付き属性です。 プロパティは、オブジェクトの性質に不可欠な属性です [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。 プロパティを変更すると、オブジェクトの意味に影響します。 次の例では、プロパティがメニュー項目に設定されている場合、ポップアップ `aria-haspopup="true"` `<li>` が表示されます。

```html
<li role="menuitem" aria-haspopup="true">Open</li>
```

状態は、オブジェクトの性質を変更しませんが、オブジェクトまたはオブジェクトとのユーザー操作に関連付けられている情報を表します。など [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) です。 たとえば、次の `aria-checked="false"` 例の状態は、チェック ボックスがオフになっていることを表します。

```html
<div role="checkbox" aria-checked="false">Accept</div>
```

W3C [の [ロール モデル](https://www.w3.org/TR/wai-aria-1.1/#roles) ] に移動して、役割、プロパティ、および状態の完全な一覧を表示します。

ARIA の詳細については、「リソース」セクションの「ARIA」 [に移動](#resources) します。

## <a name="assistive-technology-compatibility-testing"></a>支援テクノロジの互換性テスト  

作成する Web サイトが実際の支援テクノロジで動作することの確認は、障害を持つユーザーに優れたエクスペリエンスを提供するための最良の方法です。  多くの支援テクノロジがキーボードを利用していますので、Web サイトのキーボード アクセシビリティのテストを開始する際に便利です。  [キーボード互換性テストでは、][W3cPerspectiveVideosKeyboard] マウスを必要とせずにすべての対話型コントロールにアクセスできるユーザーを検証します。  Microsoft [Accessibility Insights for Web は、Microsoft][AccessibilityinsightsWebOverview] Edge と Chrome のブラウザー拡張機能であり、いくつかの一般的な問題について説明します。  

Web サイトがキーボードとうまく機能すると確信したら、スクリーン リーダーなどの他の支援テクノロジで試してみてください。  次の問題を明らかにします。

*   HTML、ARIA、CSS。  
*   機能または技術に対する支援技術のサポートレベル。  
    
異なるブラウザーでは、Microsoft Edge とは異なる方法で要素をプラットフォームアクセシビリティ API にマップする場合があります。  インターフェイスを構築する際には、それぞれの違いを考慮することが重要です。  

WebAIM では、スクリーン[][WebaimProjectsScreenreadersurvey8]リーダーと[][WebaimProjectsLowvisionsurvey2]低ビジョン ユーザーによるアンケートを実施し、テストする支援テクノロジとブラウザーを決定するのに役立ちます。  

### <a name="learning-how-to-test"></a>テスト方法の学習  

支援技術は高度なツールです。  支援技術を使用してテストをすぐに開始できると仮定して、最初に動作を確認する必要があります。  スクリーン リーダーを使ってテストする方法は、特に急な学習曲線です。  初心者のスクリーン リーダー ユーザーは、問題がスクリーン リーダーの誤用に関連している間にスクリーン リーダーのバグが発生したと考える場合があります。  

支援テクノロジによるテストの学習の詳細については、「WebAIM のスクリーン リーダーによるテスト [」][WebaimArticlesScreenreaderTesting] に移動します。  

### <a name="testing-locally"></a>ローカルでのテスト  

ほとんどのデバイスには、OS に組み込まれる支援テクノロジが含まれます。  Microsoft Windows には [、Windows ナレータースクリーン リーダー][MicrosoftSupport22798] と Windows [拡大鏡が含まれています][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。  [NVDA、FreedomscientificSoftwareJaws、ZoomText]などのサードパーティの支援テクノロジを[][FreedomscientificSoftwareZoomtext]ダウンロードできます。 [][NvaccessAboutNvda]  Apple macOS には [VoiceOver スクリーン リーダーが][AppleAccessibilityMacVision] 含まれています。  iOS、Android、Linux はすべて、さまざまな支援テクノロジをサポートしています。  

### <a name="testing-in-virtual-machines-and-emulators"></a>仮想マシンとエミュレーターでのテスト  

macOS では、Windows ナレーターや NVDA など、Windows でのみ使用できる支援テクノロジでテストする場合は、Windows 仮想マシンを作成します。  Microsoft Edge \(EdgeHTML\) と IE を持つ仮想マシンは、[仮想マシン] ダウンロード ページの VirtualBox および VMWare [で使用できます][MicrosoftDeveloperEdgeVms]。  

[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] には、Android アクセシビリティ スイートで支援テクノロジをテストする [エミュレーターが含まれています][GooglePlayStoreAndroidAccessibilitySuite]。  手順に従って仮想デバイスを[セットアップ][AndroidDeveloperDevicesManagingAvdsHtml]し、エミュレーター[][AndroidDeveloperDevicesEmulatorHtml]を起動し、GooglePlay ストアから[Android アクセシビリティ][GooglePlayStoreAndroidAccessibilitySuite]スイートをインストールします。  

> [!NOTE]
> iOS シミュレーターには、現在 VoiceOver は含めではありません。  

### <a name="cloud-based-testing-tools"></a>クラウドベースのテスト ツール  

支援テクノロジが OS で使用できない場合、または仮想マシンまたはエミュレーターにインストールできない場合は、クラウドベースの支援技術テスト ツールが次に最適です。  

*   [Assistiv Labs (商用) を][AssistivlabsMain] 使用すると、最新の Web ブラウザーを介して支援テクノロジを手動でテストできます。  支援テクノロジとブラウザーを選択すると、操作できる仮想マシン、エミュレーター、または実際のデバイスに接続されます。  

## <a name="resources"></a>リソース

### <a name="accessibility-basics"></a>アクセシビリティの基本

#### [<a name="the-a11y-project"></a>A11Y プロジェクト](http://a11yproject.com/)

A11Y プロジェクトは、Web アクセシビリティを容易にするためのコミュニティ駆動型の取り組みです。 [A11Y Project](https://a11yproject.com/)サイトを参照して、アクセシビリティの基本原則、アクセシビリティ のパターンとウィジェット[](https://a11yproject.com/patterns)ライブラリ、アクセシビリティ[](http://a11yproject.com/resources.html)ソフトウェア、ブログ、書籍、ツールに関するリソースについて説明します。

#### [<a name="web-accessibility-initiative-wai"></a>Web アクセシビリティ イニシアチブ (WAI)](https://w3.org/WAI/)

W3C Web アクセシビリティ イニシアチブ (WAI) は、Web のアクセシビリティを向上させる取り組みです。 サイトには [、Web](https://www.w3.org/WAI/gettingstarted/Overview.html)アクセシビリティの使い始 [め、包含](https://www.w3.org/WAI/users/Overview.html)の設計、チュートリアルとプレゼンテーションなど、さまざまな [リソースが](https://www.w3.org/WAI/train.html)提供されています。

### <a name="accessibility-blogs"></a>アクセシビリティブログ

#### [<a name="the-paciello-group"></a>Paciello グループ](https://www.paciellogroup.com/blog/)

Paciello グループは、世界中の組織にコンサルティングおよびテクノロジ ソリューションを提供し、政府および国際基準を満たしながら、クライアントが効果的かつ効率的にすべての対象ユーザーに確実に到達します。 ブログでは、Web アクセシビリティのベスト プラクティス、アクセシビリティ ツール、アクセシビリティの傾向に関するトピックについて説明します。

#### [<a name="simply-accessible"></a>単純にアクセス可能](http://simplyaccessible.com/articles/)

Simply Accessible は、アクセシビリティトレーニング、コンサルティングなど、Web 上のアクセシビリティの認識を変えるアクセシビリティスペシャリストのチームです。 [ [記事]](http://simplyaccessible.com/articles/) セクションでは、Web アクセシビリティ、アクセス可能なデザインなどについてのベスト プラクティスについて説明します。

#### [<a name="ssb-bart-group-ssb"></a>SSB BART グループ (SSB)](http://www.ssbbartgroup.com/blog/)

SSB BART グループは、アクセス可能な製品およびサービスの開発と展開におけるクライアントをサポートするデジタル アクセシビリティ企業です。 ブログでは、ARIA のベスト プラクティス、アクセシビリティの傾向、ウェビナーなどについて説明します。

### <a name="accessible-examples"></a>アクセス可能な例

#### [<a name="allyjs---tutorials"></a>ally.js - チュートリアル](http://allyjs.io/tutorials/)

アクセシビリティを簡単にすることで、アクセシビリティに関する懸念を持つ最新の Web アプリケーションを支援する JavaScript ライブラリ。

#### [<a name="heydonworks---aria-examples"></a>Heydonworks - ARIA の例](http://heydonworks.com/practical_aria_examples/)

アプリケーションのアクセシビリティを強化する実用的な ARIA の例

#### [<a name="openajax-examples"></a>OpenAjax の例](http://oaa-accessibility.org/)

OpenAjax Alliance Web サイトは、WAI-ARIA のルールを検証する優れたリソースであり、WAI-ARIA 実装の例を多数提供します。

#### [<a name="patterns"></a>パターン](http://a11yproject.com/patterns.html)

[A11Y Project には](http://a11yproject.com/) 、メニュー、ボタン、ツールヒントなど、アクセス可能なウィジェットやパターンのライブラリが用意されています。

### <a name="accessibility-techniques--tools"></a>アクセシビリティの手法&ツール

#### [<a name="accessibility-creating-accessible-extension-icons-for-microsoft-edge"></a>アクセシビリティ: Microsoft Edge のアクセシビリティ対応の拡張機能アイコンを作成する](/archive/microsoft-edge/legacy/developer/extensions/guides/accessibility)

Microsoft Edge のアクセス可能な拡張機能アイコンの作成に関するガイダンスを参照してください。

#### [<a name="accessible-name-and-description-computation-and-mappings-11"></a>アクセス可能な名前と説明: 計算とマッピング 1.1](https://www.w3.org/TR/accname-1.1/)

この W3C マッピング ドキュメントでは、ブラウザーが Web コンテンツ言語からアクセス可能なオブジェクトの名前と説明を決定し、アクセシビリティ API で公開する方法について説明します。

#### [<a name="accessibility-evaluation-resources"></a>アクセシビリティ評価リソース](https://www.w3.org/WAI/eval/Overview.html)

アクセシビリティ評価リソースは、Web サイトでアクセシビリティを評価するためのさまざまな方法を概説する、W3C による複数ページのリソースです。

#### [<a name="assistive-technology-compatibility-tests"></a>支援テクノロジの互換性テスト](http://www.powermapper.com/tests/)

スクリーン リーダーのような支援テクノロジ (AT) で異なるコンテンツ タイプと標準がどのように動作するのかを示すテスト結果。

#### [<a name="building-accessible-websites-just-got-a-lot-easier"></a>アクセス可能な Web サイトの構築がはるかに簡単になりました](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)

この .NET Web 開発とツールのブログ投稿では、Visual Studio [Web アクセシビリティ チェッカーについて説明します](https://go.microsoft.com/fwlink/p/?linkid=841539)。

#### [<a name="core-accessibility-api-mappings-11"></a>コア アクセシビリティ API マッピング 1.1](https://www.w3.org/TR/core-aam-1.1/)

この W3C マッピング ドキュメントでは、Web コンテンツ言語のセマンティクスがアクセシビリティ API に公開される方法について説明します。  

#### [<a name="easy-checks--a-first-review-of-web-accessibility"></a>簡単なチェック – Web アクセシビリティの最初のレビュー](https://www.w3.org/WAI/eval/preliminary.html)

WEB ページのアクセシビリティの向上に役立つ一連のクイック チェックが、WAI によって行います。

#### [<a name="how-to-meet-wcag-20"></a>WCAG 2.0 を満たす方法](https://www.w3.org/WAI/WCAG20/quickref/)

Web コンテンツ アクセシビリティ ガイドライン (WCAG) 2.0 の要件 (成功基準) と手法のクイック リファレンス。

#### [<a name="html-accessibility-api-mappings-10"></a>HTML アクセシビリティ API マッピング 1.0](https://www.w3.org/TR/html-aam-1.0/)

この W3C マッピング ドキュメントでは、HTML5.1 要素と属性がプラットフォームアクセシビリティ API にマップされる方法について説明します。

#### [<a name="quick-tips"></a>クイック ヒント](http://a11yproject.com/#Quick-tips)

[A11Y](http://a11yproject.com/)Project によるアクセシビリティに関するクイック Web 開発のヒントの一覧です。

#### [<a name="site-scan"></a>サイト スキャン](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)

Microsoft Edge デベロッパー センターのサイト スキャン ツールは、古いライブラリ、レイアウトの問題、アクセシビリティの問題をチェックします。

#### [<a name="techniques-for-wcag-20"></a>WCAG 2.0 の手法](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)

Web コンテンツ アクセシビリティ ガイドライン [(WCAG) 2.0](https://w3.org/TR/WCAG20/) の成功基準を満たす Web 開発者向けのガイダンスを提供する W3C の手法。

#### [<a name="tips-on-developing-for-web-accessibility"></a>Web アクセシビリティの開発に関するヒント](https://w3.org/WAI/gettingstarted/tips/developing.html)

障がい者がアクセスしやすい Web コンテンツの開発に関する W3C のヒント。

#### [<a name="wai-aria-authoring-practices-11"></a>WAI-ARIA オーサリング プラクティス 1.1](http://w3c.github.io/aria-practices/)

W3C のドキュメントで、読者は、WAI-ARIA 1.1 の使い方を理解し、WAI-ARIA の役割、状態、およびプロパティを使用してウィジェット、ナビゲーション、および動作をアクセス可能にする方法を推奨します。

#### [<a name="wai-guidelines-and-techniques"></a>WAI のガイドラインとテクニック](https://w3.org/WAI/guid-tech.html)

WAI によって開発された一連の Web アクセシビリティ ガイドラインと標準。  

#### [<a name="web-accessibility-evaluation-tools-list"></a>Web アクセシビリティ評価ツールの一覧](https://www.w3.org/WAI/ER/tools/index.html)

Web サイトがアクセシビリティ ガイドラインを満たしているかどうかを判断するための Web アクセシビリティ評価ツールの一覧。

#### [<a name="web-accessibility-perspectives-explore-the-impact-and-benefits-for-everyone"></a>Web アクセシビリティの観点: すべてのユーザーに対する影響と利点を確認する](https://w3.org/WAI/perspectives/)

アクセシビリティの影響とすべてのユーザーにとっての利点に関する W3C による一連の短い状況ビデオ。

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "仮想マシン |Microsoft Edge 開発者"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 "ナレーター の完全なガイド|Microsoft サポート"  
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
