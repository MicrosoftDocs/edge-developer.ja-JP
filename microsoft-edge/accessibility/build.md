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
# アクセシビリティの高い Web サイトを構築する
Web には、HTML、CSS、JavaScript の組み合わせを使って構築された動的で複雑な web サイト、アプリケーション、ユーザーインターフェイスが埋め込まれています。  ただし、アクセシビリティを考慮せずに設計および構築すると、[支援技術](https://webaim.org/articles/motor/assistive)を利用して web を参照するユーザーは、これらの複雑な web サイトを使用することが困難になります。 障碍のあるユーザーが使いやすい web サイトを構築するには、ユーザーインターフェイスに関するセマンティクス情報が必要です。 これにより、スクリーンリーダーなどの支援技術によって必要な情報を伝えることができるので、web サイトを利用することができます。

Microsoft Edge でサポートされている新しい HTML5 機能 accessibly については、 [HTML5Accessibility](https://html5accessibility.com)を参照してください。

## アクセシビリティのしくみ

支援技術により、コンピューターに通常ない機能が追加されます。 たとえば、視覚障碍のあるユーザーは、マウスと画面でブラウザーを直接使用するのではなく、スクリーンリーダーなどの支援技術と組み合わせてキーボードを使うことができます。 Microsoft プラットフォームと web 上のアプリケーションの場合、支援技術は microsoft [UI オートメーション](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、microsoft Edge のドキュメントオブジェクトモデル (DOM)、またはこれらの組み合わせなどのアプリケーション固有のオブジェクトモデルと連携します。

Web 開発者の場合は、特定の HTML 要素が UI オートメーションオブジェクトに対応しているため、これらの HTML 要素を選択するときに、開発者はこれらの要素に組み込まれているアクセシビリティプロパティとイベントを使うことができます。 通常、web サイトを作成しているときに、アプリがアクセスできるように、API が正しく書き込まれている (または適切な要素が指定されている) ことを確認するだけで十分です。 詳細については[、「Microsoft Edge で ARIA と UI オートメーション](./build/ARIA-and-UI-Automation.md)を確認する」を参照してください。  アクセシビリティの高いユニバーサル Windows プラットフォーム (UWP) アプリの詳細については、Windows デベロッパーセンターの[アクセシビリティ](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)に関するトピックを参照してください。

動的コンテンツに関する多くの一般的なアクセシビリティの問題については、適切なコーディングの方法で対処できます。 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629)ドキュメントには、よりアクセシビリティの高い動的 web アプリケーションを作成するのに役立つ多くの手法とベストプラクティスが含まれています。 ただし、適切にコードが記述されている場合でも、動的コンテンツは必ずしもアクセス可能であるとは限りません。 アクセシビリティに対応した[リッチインターネットアプリケーション (ARIA)](#aria)は、この問題を解決するのに役立ちます。  

Web アクセシビリティの詳細については、「web アクセシビリティ[イニシアチブ](https://www.w3.org/WAI/)(wai-aria 使った) による[Web アクセシビリティの概要](https://www.w3.org/WAI/intro/accessibility.php)」をご覧ください。

## ARIA
W3C's [Web Accessibility イニシアチブ](https://www.w3.org/WAI/)によるアクセシビリティ性の高い[リッチインターネットアプリケーション](https://www.w3.org/TR/wai-aria/)(ARIA) の仕様は、動的な Web コンテンツとカスタムユーザーインターフェイスをすべてのユーザーがアクセスできるようにする構文として定義されています。 ARIA は、カスタムセマンティクスを伝えるために設計された追加の属性 (ロール、プロパティ、状態) を使って HTML を拡張します。 これらの属性は、ブラウザーでコントロールの状態と役割をアクセシビリティ API に渡すために使われます。

### 役割、プロパティ、状態
ARIA ロールは、属性を使用して要素に対して設定され、 [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) 要素に関する支援技術とアクセシビリティ api 情報を提供します。 たとえば、次の `<li>` 要素は、 `role="menuitem"` メニュー内の項目であることを示すために割り当てられます。

``` html
<li role="menuitem">Home</li>
```

ARIA の状態とプロパティは、ロールの特性の定義を形成するために、オブジェクトに関する特定の情報を提供する aria のプレフィックス付き属性です。 プロパティは、やなどのオブジェクトの性質にとって重要な属性です [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。 プロパティの変更は、オブジェクトの意味に影響します。 次の例では、メニュー項目にプロパティを設定して、ポップアップがあることを示してい `aria-haspopup="true"` `<li>` ます。

``` html
<li role="menuitem" aria-haspopup="true">Open</li>
```

状態はオブジェクトの性質を変更しませんが、またはなどのオブジェクトに関連付けられたオブジェクトまたはユーザーの操作に関連する情報を表し [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) ます。 たとえば、次の例に示す状態は、 `aria-checked="false"` チェックボックスがオフになっていることを示します。

``` html
<div role="checkbox" aria-checked="false">Accept</div>
```

すべての役割、プロパティ、状態の一覧を表示するには、W3C による[役割モデル](https://www.w3.org/TR/wai-aria-1.1/#roles)に移動します。

ARIA の詳細については、「[リソース](#resources)」セクションの「aria」を参照してください。

## リソース

### アクセシビリティの基本
#### [A11Y プロジェクト](http://a11yproject.com/)
A11Y プロジェクトは、web アクセシビリティを容易にするための、コミュニティ主導の作業です。 [A11Y プロジェクト](https://a11yproject.com/)サイトでは、基本的なアクセシビリティの原則、アクセシビリティ対応のパターンとウィジェット[ライブラリ](https://a11yproject.com/patterns)、アクセシビリティソフトウェア、ブログ、書籍、ツールに関する[リソース](http://a11yproject.com/resources.html)について説明します。

#### [Web アクセシビリティイニシアチブ (WAI-ARIA 使った)](https://w3.org/WAI/)
W3C's Web Accessibility イニシアチブ (WAI-ARIA 使った) は、web のアクセシビリティを向上させるための取り組みです。 [Web アクセシビリティの使用を開始](https://www.w3.org/WAI/gettingstarted/Overview.html)するためのさまざまなリソースが用意されており、それを対象とした[デザイン](https://www.w3.org/WAI/users/Overview.html)、[チュートリアル、プレゼンテーション](https://www.w3.org/WAI/train.html)などを行うことができます。

### アクセシビリティのブログ
#### [Paciello グループ](https://www.paciellogroup.com/blog/)
Paciello グループは、世界中の組織に対してコンサルティングと技術のソリューションを提供します。顧客がすべての対象ユーザーに対して効率的かつ効率的に連絡を取ることができるようにします。 Web アクセシビリティのベストプラクティス、アクセシビリティツール、アクセシビリティの傾向などのトピックについて説明します。

#### [簡単にアクセス](http://simplyaccessible.com/articles/)
アクセシビリティのトレーニング、コンサルティングなど、web 上のアクセシビリティの認識を向上させるアクセシビリティスペシャリストのチームであるということができます。 この[セクションでは、web](http://simplyaccessible.com/articles/)アクセシビリティ、アクセシビリティの高いデザインに関するベストプラクティスについて説明します。

#### [SSB BART グループ (SSB)](http://www.ssbbartgroup.com/blog/)
SSB BART グループは、アクセシビリティ対応の製品とサービスの開発と展開において、クライアントをサポートするデジタルアクセシビリティ企業です。 これらのブログは、ARIA のベストプラクティス、アクセシビリティの傾向、ウェビナーなどのトピックに対応しています。

### アクセシビリティの高い例
#### [同盟: チュートリアル](http://allyjs.io/tutorials/)
アクセシビリティをより簡単にするために、アクセシビリティに関する問題を解決するための JavaScript ライブラリ。

#### [Heydonworks-ARIA の例](http://heydonworks.com/practical_aria_examples/)
アプリケーションのアクセシビリティを向上させるための実用的な ARIA の例

#### [OpenAjax の例](http://oaa-accessibility.org/)
OpenAjax アライアンス web サイトは、WAI-ARIA 使ったの規則を確認するための優れたリソースであり、WAI-ARIA 使ったのいくつかの実装の例を示しています。

#### [傾向](http://a11yproject.com/patterns.html)
[A11Y プロジェクトに](http://a11yproject.com/)は、メニュー、ボタン、ヒントなど、アクセシビリティ対応のウィジェットとパターンのライブラリが用意されています。

### ユーザー補助の手法 & ツール
#### [アクセシビリティ: Microsoft Edge のアクセシビリティ対応の拡張機能を作成する](../extensions/guides/accessibility.md)
Microsoft Edge のアクセシビリティ対応の拡張機能の作成に関するガイダンスを取得します。

#### [アクセシビリティ対応の名前と説明: 計算とマッピング1.1](https://www.w3.org/TR/accname-1.1/)
この W3C マッピングドキュメントでは、ブラウザーが web コンテンツ言語からアクセシビリティの高いオブジェクトの名前と説明を特定し、アクセシビリティ Api でそれらを公開する方法について説明します。

#### [アクセシビリティ評価リソース](https://www.w3.org/WAI/eval/Overview.html)
アクセシビリティ評価リソースは、アクセシビリティのために web サイトを評価するためのさまざまな方法を示す W3C のマルチページリソースです。

#### [支援技術の互換性テスト](http://www.powermapper.com/tests/)
スクリーンリーダーのように、さまざまなコンテンツの種類や標準が支援技術 (AT) でどのように動作するかを示すテスト結果。

#### [アクセシビリティの高い web サイトを作成するのがとても簡単に](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)
この .NET Web 開発とツールのブログ投稿では、Visual Studio 拡張機能の[Web アクセシビリティチェック](https://go.microsoft.com/fwlink/p/?linkid=841539)について説明します。

#### [Core Accessibility API マッピング1.1](https://www.w3.org/TR/core-aam-1.1/)
この W3C マッピングドキュメントでは、web コンテンツ言語がアクセシビリティ Api にどのように公開されるかについて説明します。  

#### [簡単なチェック– Web アクセシビリティの最初のレビュー](https://www.w3.org/WAI/eval/preliminary.html)
WAI-ARIA 使ったによって、web ページのアクセシビリティを向上させるための一連のクイックチェックが行われます。

#### [WCAG 2.0 の対応方法](https://www.w3.org/WAI/WCAG20/quickref/)
Web コンテンツのアクセシビリティガイドライン (WCAG) 2.0 の要件 (成功の条件) と手法のクイックリファレンス。

#### [HTML アクセシビリティ API マッピング1.0](https://www.w3.org/TR/html-aam-1.0/)
この W3C マッピングドキュメントでは、HTML 5.1 の要素と属性が platform accessibility Api にどのように対応するかを説明します。


#### [ポップヒント](http://a11yproject.com/#Quick-tips)
[A11Y プロジェクト](http://a11yproject.com/)でのアクセシビリティに関する web 開発のクイックヒントの一覧です。

#### [サイトのスキャン](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)
Microsoft Edge デベロッパーセンターのサイトスキャンツールは、古いライブラリ、レイアウトの問題、アクセシビリティの問題をチェックします。

#### [WCAG 2.0 の手法](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)
会議[Web コンテンツのアクセシビリティガイドライン (WCAG) 2.0](https://w3.org/TR/WCAG20/)の成功条件について web 開発者向けのガイダンスを提供する W3C の手法。

#### [Web アクセシビリティの開発に関するヒント](https://w3.org/WAI/gettingstarted/tips/developing.html)
障碍のある方にとって使いやすい web コンテンツの開発に関する W3C のヒント。

#### [WAI-ARIA 使った-ARIA のオーサリングプラクティス1.1](http://w3c.github.io/aria-practices/)
WAI-ARIA 使った-ARIA 1.1 の使用方法を理解し、WAI-ARIA 使った-ARIA の役割、状態、プロパティを使ってアクセスできるウィジェット、ナビゲーション、動作を実現するためのアプローチを提供する、W3C によるドキュメント。

#### [WAI-ARIA 使ったのガイドラインと手法](https://w3.org/WAI/guid-tech.html)
WAI-ARIA 使ったによって開発された一連の web アクセシビリティガイドラインと標準。  

#### [Web アクセシビリティ評価ツールの一覧](https://www.w3.org/WAI/ER/tools/index.html)
Web サイトがアクセシビリティガイドラインを満たしているかどうかを判断するのに役立つ web アクセシビリティ評価ツールの一覧です。

#### [Web アクセシビリティの観点: すべてのユーザーに対する影響と利点を調べる](https://w3.org/WAI/perspectives/)
アクセシビリティの影響とすべてのユーザーの利点について、W3C による一連の短いビデオ。
