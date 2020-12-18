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
# アクセス可能な Web サイトの構築

Web には、HTML、CSS、JavaScript の組み合わせを使用して構築された、動的で複雑な Web サイト、アプリケーション、およびユーザー インターフェイスが埋め込みされています。  ただし、アクセシビリティを考慮せずに設計および構築した場合、これらの複雑な Web サイトは、支援技術を利用[](https://webaim.org/articles/motor/assistive)して Web を閲覧するユーザーが使用することは困難です。 障がいのあるユーザーがアクセスできる Web サイトを構築するには、ユーザー インターフェイスに関するセマンティック情報が必要です。 これにより、スクリーン リーダーなどの支援技術は、さまざまな機能を持つユーザーが Web サイトを使用するのに役立つ必要な情報を伝えるのに役立ちます。

Microsoft Edge でサポートされている新しい HTML5 機能に関する情報については [、HTML5Accessibility](https://html5accessibility.com) にアクセスしてください。

## アクセシビリティのしくみ

支援技術によって、コンピューターには通常はない機能が追加されます。 たとえば、視覚障がいのあるユーザーは、ブラウザーをマウスや画面で直接使うのではなく、スクリーン リーダーなどの支援技術と組み合わせてキーボードを使う場合があります。 Microsoft プラットフォーム上および Web 上のアプリケーションの場合、支援技術は Microsoft [UI オートメーション](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、Microsoft Edge のドキュメント オブジェクト モデル (DOM) などのアプリケーション固有のオブジェクト モデル、またはこれらを組み合わせて操作します。

Web 開発者の場合、特定の HTML 要素は UI オートメーション オブジェクトにマップされます。そのため、これらの HTML 要素を選択する場合、開発者はそれらの要素に組み込みのアクセシビリティ プロパティとイベントを使用できます。 Web サイトを開発する場合、アプリケーションにアクセスするには、通常、API が正しく書き込まれる (または適切な要素が指定されている) 必要があります。 詳細については [、Microsoft Edge で ARIA と UI](./ARIA-and-UI-Automation.md) オートメーションを確認してください。  アクセシビリティ対応のユニバーサル Windows プラットフォーム (UWP) アプリについて[](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)詳しくは、Windows デベロッパー センターのアクセシビリティに関するトピックをご覧ください。

動的コンテンツに関する一般的なアクセシビリティの問題の多くは、適切なコーディング手法によって解決できます [。WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) のドキュメントには、よりアクセシビリティの高い動的 Web アプリケーションを作成するのに役立つ多くの手法とベスト プラクティスが含まれています。 ただし、適切にコード化されている場合でも、動的コンテンツにアクセスできるとは限りません。 [アクセス可能なリッチ インターネット アプリケーション (ARIA) は、この問題](#aria) を解決するのに役立ちます。  

Web アクセシビリティの詳細については [、「Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) Initiative (INITIATIVE) による [Web アクセシビリティの](https://www.w3.org/WAI/) 概要」を参照してください。

## ARIA

W3C の[Web アクセシビリティ](https://www.w3.org/WAI/)イニシアチブによる[Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) の仕様は、動的な Web コンテンツとカスタム ユーザー インターフェイスをすべてのユーザーがアクセス可能にするための構文として定義されています。 ARIA は、カスタム セマンティクスを伝達するように設計された追加の属性 (ロール、プロパティ、状態) を使用して HTML を拡張します。 これらの属性は、ブラウザーがコントロールの状態とロールをアクセシビリティ API に渡すのに使用されます。

### ロール、プロパティ、および状態

ARIA ロールは、この属性を使って要素に対して設定され、要素に関する支援技術とアクセシビリティ [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) API 情報を提供します。 たとえば、メニュー内の項目を示す次の要素が `<li>` `role="menuitem"` 割り当てられます。

```html
<li role="menuitem">Home</li>
```

ARIA の状態とプロパティは、オブジェクトに関する特定の情報を提供する aria-prefixed 属性であり、ロールの性質の定義を形成するのに役立ちます。 プロパティは、オブジェクトの性質に不可欠な属性です。次に例を示 [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) します [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。 プロパティを変更すると、オブジェクトの意味に影響します。 次の例では、このプロパティがポップアップを持つメニュー項目 `aria-haspopup="true"` `<li>` に設定されています。

```html
<li role="menuitem" aria-haspopup="true">Open</li>
```

状態は、オブジェクトの性質を変更しませんが、オブジェクトまたはオブジェクトとのユーザーの操作に関連付けられている情報を表します。次に示す操作を行 [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) います [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) 。 たとえば、次の `aria-checked="false"` 例の状態は、チェック ボックスがオフになっていることを表しています。

```html
<div role="checkbox" aria-checked="false">Accept</div>
```

W3C [によるロール モデル](https://www.w3.org/TR/wai-aria-1.1/#roles) に移動して、ロール、プロパティ、および状態の完全な一覧を表示します。

ARIA の詳細については、「リソース」セクションの「ARIA」を [参照](#resources) してください。

## 支援技術の互換性テスト  

構築する Web サイトが実際の支援技術で動作することの確認は、障がいのあるユーザーに適切なエクスペリエンスを提供する最善の方法です。  多くの支援技術ではキーボードを利用しています。Web サイトのキーボード アクセシビリティのテストは、最初に行うのに良い場所です。  [キーボード互換性テストでは][W3cPerspectiveVideosKeyboard] 、マウスを使わずにすべての対話型コントロールにアクセスできるユーザーを検証します。  Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] は、Microsoft Edge と Chrome のブラウザー拡張機能であり、いくつかの一般的な問題について説明します。  

キーボードで Web サイトが正常に動作すると確信したら、スクリーン リーダーなどの他の支援技術で試してみてください。  次の問題を明らかにします。

*   HTML、ARIA、および CSS。  
*   機能または技術に対する支援技術のサポート レベル。  
    
ブラウザーによって、Microsoft Edge とは異なる方法で要素がプラットフォーム アクセシビリティ API にマップされる場合があります。  インターフェイスを構築する際には、それぞれの違いを考慮することが重要です。  

WebAIM では、スクリーン[][WebaimProjectsScreenreadersurvey8]リーダーと[][WebaimProjectsLowvisionsurvey2]低ビジョン ユーザーを使用してアンケートを実施し、テストする支援技術とブラウザーを決定するのに役立ちます。  

### テスト方法の学習  

支援技術は高度なツールです。  支援技術を使用してすぐにテストを開始できると想定し、その動作について最初に知らなくても行ってください。  スクリーン リーダーを使ったテストの学習には、特に学習曲線があります。  スクリーン リーダーのユーザーは、問題がスクリーン リーダーの誤用に関連している間にスクリーン リーダーのバグが発生したと見なす場合があります。  

支援技術によるテストの学習の詳細については、「WebAIM[][WebaimArticlesScreenreaderTesting]のスクリーン リーダーによるテスト」に移動してください。  

### ローカルでのテスト  

ほとんどのデバイスには、OS に組み込まれる支援技術が含まれます。  Microsoft Windows には [、Windows ナレーター スクリーン リーダー][MicrosoftSupport22798] と Windows [拡大鏡が含まれています][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。  [NVDA、FreedomscientificSoftwareJaws、ZoomText]などのサードパーティの支援技術を[][FreedomscientificSoftwareZoomtext]ダウンロードできます。 [][NvaccessAboutNvda]  Apple macOS には [VoiceOver スクリーン リーダー][AppleAccessibilityMacVision] が含まれています。  また、iOS、Android、Linux はすべて、さまざまな支援技術をサポートしています。  

### 仮想マシンとエミュレーターでのテスト  

macOS では、Windows ナレーターや NVDA など、Windows でのみ利用可能な支援技術でテストする場合は、Windows 仮想マシンを作成します。  Microsoft Edge \(EdgeHTML\) と IE を持つ仮想マシンは、仮想マシンのダウンロード ページで VirtualBox と VMWare [で利用できます][MicrosoftDeveloperEdgeVms]。  

[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] には、Android アクセシビリティ スイートで支援技術をテストするエミュレーター [が含まれています][GooglePlayStoreAndroidAccessibilitySuite]。  指示に従 [って仮想デバイス][AndroidDeveloperDevicesManagingAvdsHtml] をセットアップ [し、エミュレーター][AndroidDeveloperDevicesEmulatorHtml]を起動し、GooglePlay ストアから Android アクセシビリティ [スイート][GooglePlayStoreAndroidAccessibilitySuite] をインストールします。  

> [!NOTE]
> 現在、iOS シミュレーターには VoiceOver は含めではありません。  

### クラウドベースのテスト ツール  

OS で支援技術が利用できない場合や、仮想マシンやエミュレーターにインストールできない場合は、次に最適なツールはクラウド ベースの支援技術テスト ツールです。  

*   [Assistiv Labs (商用)][AssistivlabsMain] を使用すると、最新の Web ブラウザーを使用して支援技術を手動でテストできます。  支援技術とブラウザーを選択し、操作する可能性のある仮想マシン、エミュレーター、または実際のデバイスに接続します。  

## リソース

### アクセシビリティの基本

#### [A11Y プロジェクト](http://a11yproject.com/)

A11Y プロジェクトは、Web アクセシビリティを容易にするためのコミュニティ型の取り組みです。 [A11Y プロジェクト](https://a11yproject.com/)サイトで、基本的なアクセシビリティの原則、アクセシビリティ 対応のパターンとウィジェット[](https://a11yproject.com/patterns)ライブラリ、アクセシビリティ[](http://a11yproject.com/resources.html)ソフトウェア、ブログ、書籍、ツールに関するリソースについて説明します。

#### [Web Accessibility Initiative (INITIATIVE)](https://w3.org/WAI/)

W3C Web Accessibility Initiative (INITIATIVE) は、Web のアクセシビリティを向上させる取り組みです。 サイトには[、Web](https://www.w3.org/WAI/gettingstarted/Overview.html)アクセシビリティの使用の開始、包含のための設計、チュートリアルや[](https://www.w3.org/WAI/users/Overview.html)プレゼンテーションなど、さまざまなリソース[](https://www.w3.org/WAI/train.html)が提供されています。

### アクセシビリティに関するブログ

#### [Paciello グループ](https://www.paciellogroup.com/blog/)

Paciello グループは、世界中の組織にコンサルティングおよびテクノロジ ソリューションを提供し、クライアントがすべての対象ユーザーに効果的かつ効率的に到達し、同時に政府および国際基準を満たします。 ブログでは、Web アクセシビリティのベスト プラクティス、アクセシビリティ ツール、アクセシビリティの傾向などについて説明します。

#### [単純にアクセス可能](http://simplyaccessible.com/articles/)

Simply Accessible は、アクセシビリティ トレーニングやコンサルティングなど、Web 上のアクセシビリティの認識を変えるアクセシビリティ スペシャリストのチームです。 「 [記事」](http://simplyaccessible.com/articles/) セクションでは、Web アクセシビリティ、アクセシビリティ対応の設計などについてのベスト プラクティスについて説明します。

#### [SSB BART グループ (SSB)](http://www.ssbbartgroup.com/blog/)

SSB BART グループは、アクセシビリティ対応の製品とサービスの開発と展開を顧客にサポートするデジタル アクセシビリティ企業です。 ブログでは、ARIA のベスト プラクティス、アクセシビリティの傾向、ウェビナーなどについて説明しています。

### Accessible Examples

#### [ally.js - チュートリアル](http://allyjs.io/tutorials/)

アクセシビリティを簡単にすることで、アクセシビリティに関する最新の Web アプリケーションを支援する JavaScript ライブラリ。

#### [Heydonworks - ARIA の例](http://heydonworks.com/practical_aria_examples/)

アプリケーションのアクセシビリティを強化する実用的な ARIA の例

#### [OpenAjax の例](http://oaa-accessibility.org/)

OpenAjax Alliance の Web サイトは、RIA-ARIA の規則を検証する優れたリソースであり、なにかの一例を示しています。

#### [パターン](http://a11yproject.com/patterns.html)

[A11Y プロジェクトは](http://a11yproject.com/) 、メニュー、ボタン、ヒントなど、アクセス可能なウィジェットとパターンのライブラリを提供します。

### アクセシビリティの手法と&ツール

#### [アクセシビリティ: Microsoft Edge のアクセシビリティ対応の拡張機能アイコンの作成](../../edgehtml/extensions/guides/accessibility.md)

Microsoft Edge のアクセス可能な拡張機能アイコンの作成に関するガイダンスを提供します。

#### [アクセス可能な名前と説明: 計算とマッピング 1.1](https://www.w3.org/TR/accname-1.1/)

この W3C マッピング ドキュメントでは、Web コンテンツ言語からアクセス可能なオブジェクトの名前と説明をブラウザーが決定し、アクセシビリティ API で公開する方法について説明します。

#### [アクセシビリティ評価リソース](https://www.w3.org/WAI/eval/Overview.html)

アクセシビリティ評価リソースは、アクセシビリティを考慮して Web サイトを評価するためのさまざまなアプローチの概要を示す、W3C によるマルチページ リソースです。

#### [支援技術の互換性テスト](http://www.powermapper.com/tests/)

スクリーン リーダーのような支援技術 (AT) で異なるコンテンツ タイプと標準がどのように動作するのかを示すテスト結果。

#### [アクセス可能な Web サイトの構築が簡単になりました](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)

この .NET Web 開発とツールのブログ投稿では、Web アクセシビリティ チェックのVisual Studio [について説明します](https://go.microsoft.com/fwlink/p/?linkid=841539)。

#### [コア アクセシビリティ API マッピング 1.1](https://www.w3.org/TR/core-aam-1.1/)

この W3C マッピング ドキュメントでは、Web コンテンツ言語のセマンティクスがアクセシビリティ API に公開される方法について説明します。  

#### [簡単なチェック – Web アクセシビリティの最初のレビュー](https://www.w3.org/WAI/eval/preliminary.html)

WEB ページのアクセシビリティに対応するのに役立つ、一連の QUICK Checks が、THE を使用して行います。

#### [WCAG 2.0 を満たす方法](https://www.w3.org/WAI/WCAG20/quickref/)

Web コンテンツ アクセシビリティ ガイドライン (WCAG) 2.0 の要件 (成功基準) と手法のクイック リファレンスです。

#### [HTML アクセシビリティ API マッピング 1.0](https://www.w3.org/TR/html-aam-1.0/)

この W3C マッピング ドキュメントでは、HTML5.1 要素と属性をプラットフォーム アクセシビリティ API にマップする方法について説明します。

#### [クイック ヒント](http://a11yproject.com/#Quick-tips)

A11Y プロジェクトによるアクセシビリティに関するクイック [Web 開発のヒントの一覧](http://a11yproject.com/)です。

#### [サイト スキャン](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)

Microsoft Edge デベロッパー センターのサイト スキャン ツールは、古いライブラリ、レイアウトの問題、アクセシビリティの問題をチェックします。

#### [WCAG 2.0 の手法](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)

Web コンテンツ アクセシビリティ ガイドライン [(WCAG) 2.0](https://w3.org/TR/WCAG20/) の成功基準を満たす Web 開発者向けのガイダンスを提供する W3C の手法。

#### [Web アクセシビリティの開発に関するヒント](https://w3.org/WAI/gettingstarted/tips/developing.html)

障がいのある方がアクセスしやすい Web コンテンツの開発に関する W3C からのヒント。

#### [RIA-ARIA Authoring Practices 1.1](http://w3c.github.io/aria-practices/)

W3C のドキュメント。READERS-ARIA 1.1 の使い方を読者に理解し、WIDGETS-ARIA の役割、状態、およびプロパティを使用してウィジェット、ナビゲーション、および動作にアクセス可能な方法を推奨します。

#### [GUIDELINE のガイドラインと手法](https://w3.org/WAI/guid-tech.html)

一連の Web アクセシビリティ ガイドラインと、ANDSY が開発した標準。  

#### [Web アクセシビリティ評価ツールの一覧](https://www.w3.org/WAI/ER/tools/index.html)

Web サイトがアクセシビリティ ガイドラインを満たしたかどうかを判断するのに役立つ Web アクセシビリティ評価ツールの一覧です。

#### [Web アクセシビリティの観点: すべてのユーザーに対する影響と利点を探る](https://w3.org/WAI/perspectives/)

アクセシビリティの影響とすべてのユーザーに対するメリットに関する W3C による一連の短い状況に関するビデオ。

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
