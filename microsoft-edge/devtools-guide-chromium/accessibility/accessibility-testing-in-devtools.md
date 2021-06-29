---
description: DevTools を使用したアクセシビリティの問題のテストの開始
title: DevTools を使用したアクセシビリティ テストの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f6ec0652bbbb7d7e60a69877a9d44a7a2fd636a5
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624795"
---
# <a name="overview-of-accessibility-testing-using-devtools"></a>DevTools を使用したアクセシビリティ テストの概要

この記事では、DevTools でアクセシビリティの問題をテストするために使用できる機能の一部について取り上げ、取り上げを行います。  DevTools のさまざまな機能を使用してデモ ページのアクセシビリティの問題を検出し、それらを修正する方法について説明します。  新しい [タブでデモ ページ][DevToolsA11yErrorsDemopage] を開き、自分で試し、一緒にテストできます。

:::image type="complex" source="../media/a11y-testing-basics-demopage.msft.png" alt-text="この記事で使用されるデモ ページには、アクセシビリティに関する問題がいくつか含まれる" lightbox="../media/a11y-testing-basics-demopage.msft.png":::
    この記事で使用されるデモ ページには、アクセシビリティに関する問題がいくつか含まれる
:::image-end:::


## <a name="automated-testing-by-using-the-issues-tool"></a>問題ツールを使用した自動テスト

ブラウザーでデモ ページを開き、DevTools を開いた場合は、問題カウンターで一部の問題が自動的に **検出されます**。  [問題 **] カウンター** \( Issues counter \) を選択して[問題] ツールを開き、問題と ![ ](../media/issues-counter-icon.msft.png) 詳細を表示します。 [][DevToolsIssuesTool]

:::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text="[問題] カウンターは、現在の Web ページに発生している問題の数を示し、[問題] ツールを開きます。" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
    [問題] カウンターは、現在の Web ページに発生している問題の数を示し、[問題] ツールを開きます。
:::image-end:::

この記事では、問題ツールの **[アクセシビリティ** ] セクション **に注目** します。

:::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="[問題] ツールに表示されるアクセシビリティの警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
    [問題] ツールに表示されるアクセシビリティの警告
:::image-end:::

チュートリアルの詳細な手順については、[問題] ツールの [ [アクセシビリティの表示] セクションに移動します][DevToolsAccessibilityTestIssuesToolViewAccSection]。


### <a name="automatically-checking-that-input-fields-have-labels"></a>入力フィールドにラベルが含まれていますを自動的に確認する

最初に表示される警告はです `Form elements must have labels: Element has no title attribute. Element has no placeholder attribute` 。  このセクションを展開し、[要素で開**** く] リンクを選択**** すると、[要素] ツールが開き、DOM ツリーで要素が強調表示されます。  [ **スタイル]** タブには、要素に適用される CSS が表示されます。

チュートリアルの詳細な手順については、「入力フィールドにラベル [が付い確認する」に移動します][DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]。

:::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="[問題] ツールでリンクを選択した後に問題のある HTML を表示する要素ツール" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
    [問題] ツールでリンクを選択した後に問題のある HTML を表示する要素ツール
:::image-end:::

この場合、HTML には機能 `label` しない要素があります。

```html
<label>Search</label>
<input type="search">
<input type="submit" value="go">
```

要素と要素の間に接続しないので、ここでの要素の使用 `label` は間違 `label` `input` っています。  検索ラベルを選択すると、有効な HTML ラベルが検索入力テキスト ボックスに **フォーカスを置** く場合があります。 

この問題は、要素に要素をネストするか、要素の属性をポイントする属性を追加 `input` `label` `for` `id` することで解決 `input` できます。  正しい接続を表示するには、寄付フォームの **[その** 他] ラベルを選択します。

[問題] ツールで説明リンクを選択 **して、この** 情報を取得することもできます。

:::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="問題に関する詳細な情報を示す Issues ツール内のリンク" lightbox="../media/a11y-testing-more-information-links.msft.png":::
    問題に関 **する詳細** な情報を示す Issues ツール内のリンク
:::image-end:::


### <a name="automatically-checking-that-images-have-alt-text"></a>画像に代替テキストが含まれていますを自動的に確認する

もう 1 つの自動的に検出された問題は、ページ内の画像の多くに代替テキストが含めなかった場合です。  警告を展開すると `Images must have alternate text: Element has no title attribute` 、その問題を抱える 4 つのイメージ インスタンスが表示されます。

:::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="代替テキストが見つからない画像を報告する問題ツール" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
    代替 **テキストが見** つからない画像を報告する問題ツール
:::image-end:::

チュートリアルの詳細な手順については、「イメージに代替テキストが含まれています。」 [に移動します][DevtoolsAccessibilityTestIssuesToolCheckAltText]。


### <a name="automatically-checking-that-text-colors-have-enough-contrast"></a>テキストの色に十分なコントラストを自動的に確認する

問題 **ツールは** 、ページ上の 2 つの要素のコントラストが十分ではない場合にも報告します。

:::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="[問題] ツールで報告されたコントラストの問題" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
    [問題] ツールで報告された **コントラストの** 問題
:::image-end:::

[ **問題]** ツールは、警告の詳細な説明を提供します。  ドリルダウンすると、この問題がある要素の一覧が表示されます。  [問題 **] ツール** で、要素をポイントするリンクを選択すると、レンダリングされたページ上のその要素が強調表示されます。

:::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="ページへのリンクを選択した後に強調表示されたページ内の要素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
    ページへのリンクを選択した後に強調表示されたページ内の要素
:::image-end:::

チュートリアルの詳細な手順については、「テキストの色に [十分なコントラストが含まれます。」に移動します][DevtoolsAccessibilityTestIssuesToolCheckContrast]。


### <a name="verify-that-the-webpage-layout-is-usable-when-narrow"></a>狭い場合に Web ページ レイアウトが使用可能な場合を確認する

<!-- by design, this section doesn't have a corresponding how-to article -->

アクセシビリティの重要な部分は、狭いビューポートで Web 製品が正しく動作することが重要です。 多くのユーザーは、ページを使用するためにページをズームする必要があります。つまり、スペースがあまり残っていないという意味です。 スペースが足りない場合は、複数列のレイアウトを 1 列のレイアウトに変換し、コンテンツを理解できる順序で配置する必要があります。 つまり、最も重要なコンテンツをページの上部に配置し、追加のコンテンツをページの下に配置します。

ブラウザー ウィンドウを狭くし、矢印キーを使用してページをスクロールすると、デモ ページの上部のナビゲーション バーにアクセシビリティの問題があるのが分かっています。  上のナビゲーション バーは、 **前の画像** に示すように[検索] フォームと重なり、その問題を修正する必要があります。

狭いビューポートをシミュレートするには、ブラウザー ウィンドウのサイズを変更しますが、デザインの応答性をテストするには **、Device エミュレーション ツールを使用する方が良い方法** です。  任意の Web サイトのアクセシビリティの問題 **を** 見つけるのに役立つデバイス エミュレーション ツールの機能を次に示します。

*  ブラウザー ウィンドウのサイズを変更せずに、ページのサイズを変更し [、CSS][DevToolsMediaQueries] メディア クエリがレイアウトの変更をトリガーするかどうかをテストします。
*  マウスを使用する依存関係を確認します。 既定では、デバイス エミュレーションはタッチ デバイスを前提とします。 つまり、ホバー操作に依存する製品の機能は機能しません。 
*  さまざまなデバイス、ズーム レベル、ピクセル比をシミュレートして視覚的なテストを行います。
*  製品が不当な接続でどのように動作するか、またはユーザーがオフラインである場合にテストします。  低速の接続でユーザーに最も重要な操作を表示する方法も、アクセシビリティに関する考慮事項です。

デバイス エミュレーション ツールの詳細**については、「デバイス**の DevTools でモバイル デバイスをエミュレート[するMicrosoft Edge移動します][DevToolsDeviceModeIndex]。


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a>DOM ツリーの波の下線は、自動的に検出された問題を示します

要素ツールの DOM ツリー **は** 、波状の下線を追加することで、HTML 内の問題に直接フラグを自動的に設定します。  波線 `Shift` + `click` が付く要素がある場合は、[問題] ツール**が**開きます。

:::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="DOM ツリーに波線付き下線が表示されている要素には問題があります。  Shift キーを押しながら要素をクリックすると、問題に直接アクセスできます。" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
    DOM ツリーに波線付き下線が表示されている要素には問題があります。  `Shift`+`click` 問題に直接アクセスする要素。
:::image-end:::

Issues ツールで見つかったこれらの**** 問題は、回避できる比較的明白なアクセシビリティの問題です。  Issues **ツールとその** ガイド付き説明を使用して修正すると、アクセス可能な製品に向かう途中で設定されます。


## <a name="limits-of-automated-testing"></a>自動テストの制限

Issues[ツール、][DevToolsIssuesTool][アクセシビリティ][AccessibilityInsights]インサイト、[およびライト][Lighthouse]ハウスは、Web ページのアクセシビリティ レポートを自動的に生成するツールです。  このようなツールから自動レポートを取得できるのは、アクセシビリティ テストの開始にすぎない。

アクセシビリティとは、さまざまな技術的な環境で製品を使用するさまざまなニーズを持つユーザーとの対話に関する情報です。  このテストは完全に自動化できないが、製品をナビゲートする人間による検証が必要です。  最適なシナリオでは、アクセシビリティのニーズが異なるテスターや、さまざまな環境を使用するテスターにアクセスできます。  しかし、キーボードを使用してナビゲーションを行い、ページの異なる部分を検査することで、自分で多くのことを行う必要があります。

デモ ページには、自動テストで検出できない追加の問題があります。 

*  ページを操作した後に発生する問題。 
*  ウィンドウを狭くするなどの表示の変更に関連する問題。

これらの問題の 1 つは、寄付フォームです。  マウスを使用する場合は、さまざまなオプションをクリックして寄付することができます。  しかし、キーボードを使用して寄付フォームにアクセスしようとすると、何も起こりません。 この問題を解決するには、検査ツールを使用する **必要** があります。

:::image type="complex" source="../media/a11y-testing-basics-donation-form-issue.msft.png" alt-text="デモ ページの寄附フォームが強調表示されます" lightbox="../media/a11y-testing-basics-donation-form-issue.msft.png":::
    デモ ページの寄附フォームが強調表示されます
:::image-end:::


## <a name="using-the-inspect-tool-to-detect-accessibility-issues"></a>[検査] ツールを使用してアクセシビリティの問題を検出する

[検査 **] ツール** を使用して、Web ページの一部にカーソルを合わせると、アクセシビリティの問題を検出できます。  Inspect **** \( ![ Inspect ](../media/inspect-icon.msft.png) \) ツールは、DevTools の左上隅にあります。  [検査] ツール ボタンを選択して、[検査] **ツールを** オンにします。

:::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="[検査] ツール ボタンを選択して[検査] ツールをオンにする" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
    [ **検査]** ツール ボタンを選択して[検査] **ツールを** オンにする
:::image-end:::

[ツールの検査] **ボタンを** 選択した後、レンダリングされたページの任意の要素の上にポインターを移動できます。  [検査] ツールは、要素のレイアウトを多色のフレックスボックス オーバーレイとして表示し、要素の詳細をヒントに似た情報オーバーレイとして表示します。

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報オーバーレイ" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報**オーバーレイ**
:::image-end:::

[検査] ツールの [ **アクセシビリティ] セクション** には、該当する **場合はコントラスト** 線が含まれます。

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="[検査] ツールの [アクセシビリティ] セクションには、該当する場合はコントラスト線が含まれます。" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    [検査] ツールの **[アクセシビリティ] セクション** には、 **該当する場合はコントラスト** 線が含まれます。
:::image-end:::

詳細なチュートリアル手順については、「色の強調表示を [使用して入れ子になった領域を識別する」に移動します][DevtoolsAccessibilityTestInspectToolColorHighlighting]。
<!-- = test-inspect-tool.md##identify-nested-regions-using-color-highlighting -->

検査ツールの **情報オーバーレイの** 上部には、次の情報が表示されます。

* レイアウトの種類。要素がフレックスボックスまたはグリッドを使用して配置されている場合は、適切なアイコン \(![グリッド レイアウト アイコン](../media/grid-icon.msft.png)\).
* 要素の名前 **(a、h1、div****など)。** ****
* 要素のサイズ (ピクセル単位)。
* 色は、色見本 (小さい色付き四角形) として、書式設定された値 (など) として表示されます `#336699` 。
* フォント情報 (サイズとフォント ファミリ)。
* 余白とパディング (ピクセル単位)。

Inspect **オーバーレイの** アクセシビリティ **部分** については、次のセクションで説明します。


### <a name="checking-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a>個々の要素でテキストのコントラスト、スクリーン リーダー テキスト、キーボードのサポートを確認する

[ **検査] オーバーレイの** [アクセシビリティ] **セクション** には、次の行が含まれます。

*   **コントラスト** は、視覚障害を持つユーザーが要素を理解できるかどうかを定義します。
    *   [WCAG][WCAG] [ガイドラインで定義][W3CContrastRatio]されているコントラスト比は、テキストと背景色の間に十分なコントラストが含されているかどうかを示します。  緑色のチェック マーク アイコンは十分なコントラストを示し、オレンジ色の感嘆符アイコンは十分なコントラストが見えない状態を示します。

*   **名前** と **役割は** 、スクリーン リーダーなどの情報支援テクノロジが要素について報告する情報を示します。
    *   Name **は** 、要素のテキスト コンテンツ `a` です。  要素の場合 `<a href="/">About Us</a>` 、 **検査ツールに** 表示される名前は "About Us" です。
    *   要素**の Role。**  Role **は** 、通常、要素名 `article` (、 `img` `link` `heading` など) です。  と `div` 要素 `span` はとして表されます `generic` 。

*   **キーボードフォーカス可能は** 、ユーザーがマウス以外の入力デバイスを使用して要素に到達できるかどうかを示します。
    *   緑色のチェック マーク アイコンは、要素がキーボードフォーカス可能な状態を示します。
    *   斜めの線が付く灰色の円は、要素がキーボードフォーカス可能でなかったかどうかを示します。

チュートリアルの詳細な手順については、「テキストのコントラスト、スクリーン リーダー テキスト、キーボードのサポートについて個々の要素を確認する」 [に移動します][DevtoolsAccessibilityTestInspectToolIndivElems]。
<!-- = test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support -->


### <a name="using-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a>[検査] ツールを使用して Web ページにカーソルを合わせると、DOM と CSS が強調表示されます。

[検査] **ツールを使用** する場合、レンダリングされたページで要素を選択すると、[要素] ツール **が開** きます。  DOM ツリーには要素の HTML が表示され **、Styles** には要素に適用される CSS プロパティが表示されます。

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="要素ツールに表示される選択した要素の詳細" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    要素ツールに表示される選択した要素の詳細
:::image-end:::

[検査] **ツールを** 使用する場合、レンダリングされたページの異なる部分にカーソルを合わせると、 **要素** が開いていると、DOM ツリーが自動的に更新されます。

チュートリアルの詳細な手順については、「検査ツールを使用して Web ページにカーソルを合わせる」に移動して、DOM と [CSS を強調表示します][DevtoolsAccessibilityTestInspectToolDomCss]。
<!-- = test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css -->


## <a name="verify-keyboard-support-by-using-the-tab-and-enter-keys"></a>Tab キーと Enter キーを使用してキーボードのサポートを確認する

すべてのユーザーがポインターデバイスやタッチ デバイスを使用する場合や、低視力の人もいます。 これらのシナリオに対応するには、UIs がキーボードで動作します。

キーボードを使用して、要素から要素へのジャンプを使用して、ページを `Tab` `Shift+Tab` 移動するテストを行います。  デモ ページを押すと、最初にフォーカスを受け取ったのは、ページ ヘッダーの `Tab` **[検索** ] フォームです。  [ `Enter` 問題] ツールを使用するときに以前に発見したラベルの問題にもかかわらず、フォームを送信することもできます。 ****

詳細なチュートリアル手順については、「Tab キーと Enter キーを使用してキーボードサポートを確認 [する」に移動します](test-tab-enter-keys.md)。

代わりに押すと、フォーカスを取得する次の要素は、アウトラインで示されているページのコンテンツ セクションの最初の [その他] `Tab` `Enter` リンクです。 ****

:::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="Tab キーを使用してページを移動します。  ページの [その他] リンクにフォーカスが表示されます。" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
    キーを使用してページを移動 `Tab` します。  ページの [その他] **リンクに** フォーカスが表示されます。
:::image-end:::

最後の [その他] **リンクを** 過ぎた後、ページが上にスクロールし、フォーカスがある要素が不明です。

画面の左下を見た場合、またはスクリーン リーダーを使用する場合は、ブラウザーに URL が表示されるので、サイドバー ナビゲーション メニューの青い**Cats**リンクにフォーカスが設定されている場合があります。 `#cats`

:::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="フォーカスのスタイルが不足すると、ページの現在の場所を知ることは不可能です。  唯一のヒントは、ウィンドウの左下にリンク ターゲットが表示されます。" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
    フォーカスのスタイルが不足すると、ページの現在の場所を知ることは不可能です。  唯一のヒントは、ウィンドウの左下にリンク ターゲットが表示されます。
:::image-end:::

もう一 `Tab` 度選択すると、寄付フォームの入力テキスト ボックスにアクセスします。  ただし、入力テキスト ボックスの **上にある 50**ボタン **、100** ボタン、 **または 200** ボタンには到達できない。  また、その入力テキスト ボックスにフォーカスがある場合、選択 `Enter` してもフォームは送信されます。

:::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="寄附フォームのキーボードアクセス可能な要素は、入力テキスト フィールドのみです。" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
    寄附フォームのキーボードアクセス可能な要素は、テキスト フィールドのみです。
:::image-end:::

もう一度選択すると、トップ ナビゲーション バーにフォーカスが置き、ページの別のセクションまたはサイトの別のページに `Tab` `Enter` 移動できます。  フォーカスアウトラインがあるから、どの要素をオンにしているのか分かっている。  トップ ナビゲーション バーでリンクを選択するには、リンクにフォーカスを設定するか、を選択 `Tab` `Shift+Tab` します `Enter` 。

:::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="上部のナビゲーション バーには強調表示とフォーカスのアウトラインが表示され、キーボードにアクセスできます。" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
    上部のナビゲーション バーには強調表示とフォーカスのアウトラインが表示され、キーボードにアクセスできます。
:::image-end:::

ここで修正する問題がいくつか見つかりました。

* キーボードを使用してページ上を移動する場合、サイドバーのナビゲーション メニューにフォーカスがあるユーザー `Tab` は表示されます。
* 寄附フォームでは、キーボードを使用する場合、**50、100、**、 **および 200** のボタンとフォーム送信機能は機能しません。
* キーボードのタブの順序が正しくありません。 キー `Tab` は、サイドバー ナビゲーション**** メニューの前のページ上のすべての [その他] リンクを移動します。  この順序は、そのページの別のセクションに移動することを目的としたサイドバー ナビゲーションなので `Tab` 役に立つとは限らない。 

DevTools を使用してこれらの問題を分析しましょう。


## <a name="analyze-keyboard-accessibility-issues-using-devtools"></a>DevTools を使用してキーボードアクセシビリティの問題を分析する


### <a name="analyzing-the-lack-of-indication-of-keyboard-focus-in-the-sidebar-menu"></a>サイドバー メニューでのキーボード フォーカスの表示の不足を分析する

キーボードで使用するためにサイドバー ナビゲーションが期待通り最適化されていない理由を確認するには、まず[検査] ツール**** を使用してサイドバー ナビゲーション メニューのリンクを強調表示してから、DOM ツリーで要素にドリルダウンします。 `a` 

:::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="サイドバーのナビゲーション メニューでリンクのソース コードと適用されたスタイルを確認する" lightbox="../media/a11y-testing-menu-link.msft.png":::
    サイドバーのナビゲーション メニューでリンクのソース コードと適用されたスタイルを確認する
:::image-end:::

[スタイル **] タブ** で、リンクに適用される CSS を確認できます。リンク先を選択すると、[ソース] ツールでファイル `styles.css` **が開** きます。

:::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="リンクに適用されるスタイル (ソース ツールに表示)" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
    リンクに適用されるスタイル (ソース ツールに表示)
:::image-end:::

上記の例では、マウスを使用する場合、ページのスタイルにはメニュー項目の状態が含まれますが、キーボード ユーザーの CSS には `hover` `focus` 状態はありません。  

また、この例では、リンクはを使用します `outline: none` 。 このスタイルは、フォーカスとキーボードが使用されている場合に、ブラウザーによって要素に自動的に追加されるアウトラインを削除するために使用されます。  この問題を回避するには、使用しないようにします `outline: none` 。

チュートリアルの詳細な手順については、「サイドバー メニューのキーボード フォーカスの不足を分析 [する」に移動します](test-analyze-no-focus-indicator.md)。


### <a name="analyzing-the-lack-of-keyboard-support-in-the-donation-form"></a>寄附フォームでのキーボード サポートの不足の分析

寄付フォームのボタンは、フォームのコントロールとして自動テスト ツールでは認識されない要素を使用 `div` して実装されます。

これを調査するには、[検査] ツール**** を使用して、寄付フォームのボタンの上にマウス ポインターを置きます。  その結果、情報オーバーレイのキーボードフォーカス可能な行の灰色のリングで示されている、キーボードにアクセス**** できる値はありません。  情報オーバーレイの **[名前**] 行と [役割] 行に示すように、寄附フォームのボタンには名前も含め、(要素を表す) 役割があります。つまり、支援テクノロジにはアクセスできないという意味です。 **** `generic` `div` `span`

:::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
    フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。
:::image-end:::

チュートリアルの詳細な手順については、「フォーム内のキーボード サポートの不足を [分析する」に移動します](test-analyze-no-keyboard-support.md)。

**[Donate] ボタンを選択**すると、[**検査**] ツールが****[要素] ツールに移動し、フォームの HTML を表示します。

```HTML
<div class="donationrow">
    <div class="donationbutton">50</div>
    <div class="donationbutton">100</div>
    <div class="donationbutton">200</div>
</div>
<div class="donationrow">
    <label for="freedonation">Other</label>
    <input id="freedonation" class="smallinput">
</div>
<div class="donationrow">
    <div class="submitbutton">Donate</div>
</div>
```

and 要素の使用は有効であり、ラベルは意図した通り動作し、テキスト ボックスは `label` `input` `input` キーボードでアクセスできます。  フォームの残りの部分では要素が使用されますが、スタイルは簡単ですが `div` 、意味的な意味はありません。

次に、フォームの JavaScript 機能を分析します。 [ **要素]** で、[ **イベント リスナー] タブを選択** して、フォームの JavaScript を分析します。

:::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text="フォームの JavaScript へのリンクを含む [イベント リスナー] タブ" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
    フォーム **の JavaScript** へのリンクを含む [イベント リスナー] タブ
:::image-end:::

[イベント**リスナー] タブ**で、リンクを選択して [ソース] ツールを開き、フォームの機能を担当する `buttons.js:18` JavaScript を調えます。 ****

:::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="[ソース] ツールに表示される、寄付フォームの機能を担当する JavaScript" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
    [ソース] ツールに表示される、寄付フォームの機能を担当する**JavaScript**
:::image-end:::

イベントはマウス ポインターとキーボードの両方で動作しますので、ボタンでイベントを使用 `click` `click` する方法をお勧めします。  ただし、要素はキーボードでアクセスできないので、Donate ボタンは要素として実装されます。この JavaScript はマウスを使用する場合 `div` **** `div` にのみ実行されます。

ボタンとしての使用は、要素が提供する機能を作成するために追加の JavaScript が必要な `div` 従来の `button` 例です。 その結果、アクセスできないエクスペリエンスが発生します。


### <a name="checking-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a>アクセシビリティ ツリーでキーボードとスクリーン リーダーのサポートを確認する

[検査 **] ツール** を使用してページ上の各要素を個別に確認するには、時間がかかります。  代わりに、[アクセシビリティ] **タブを使用** して、ページの **アクセシビリティ ツリーを移動します**。  アクセシビリティ ツリーは、ページがスクリーン リーダーなどの支援テクノロジに提供する情報を示します。

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="アクセシビリティ ツリーの [寄附フォーム] ボタン" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    アクセシビリティ ツリーの **[寄附フォーム] ボタン**
:::image-end:::

名前を持たなかったり、役割を持つツリー内の要素は、キーボード ユーザーや支援技術を使用しているユーザーが使用できないので、問題です `generic` 。

チュートリアルの詳細な手順については、「アクセシビリティ ツリーでキーボードとスクリーン リーダーのサポートを確認 [する」に移動します](test-accessibility-tree.md)。


### <a name="analyzing-the-order-of-keyboard-access-to-sections-of-the-page"></a>ページのセクションへのキーボード アクセスの順序を分析する

もう 1 つの問題は、ページの不明瞭なタブオーダーです。  キーボード ユーザーは、ページ全体のすべての [その他] リンクをタブ移動した **後にのみ、** サイドバー ナビゲーション メニューに移動します。  この例では、サイドバーのナビゲーション メニューは、そのページの別のセクションへのショートカットを意図しています。  このタブオーダーは、ユーザー エクスペリエンスが低下します。 

わかりにくい順序の理由は、ドキュメントのソースの `Tab` 順序によって決まるからです。  タブオーダーは、既定のソース順序からその要素を取り出す要素の属性を使用して `tabindex` 変更することもできます。

ドキュメントのソース コードでは、ページのメイン コンテンツの後にサイドバー ナビゲーション メニューが表示されます。  サイドバーナビゲーション メニューは、CSS を使用してサイドバー ナビゲーション メニューが配置されている場合にのみ、ページのメイン コンテンツの上に表示されます。

ドキュメントのソースの順序は、支援テクノロジにとって重要であり、レンダリングされたページに要素が表示される順序とは異なる場合があります。  CSS を使用すると、視覚的な方法でページ要素の順序を変更できますが、スクリーン リーダーなどの支援テクノロジは、その CSS と同じ順序でページ要素を表すという意味ではありません。

ページ要素の順序をテストするには、[アクセシビリティ] タブの **[ソース** オーダー ビューアー **] を使用** します。 下にスクロールして、[ソースの順序を **表示] チェック ボックスをオン** にします。  要素の選択など、 **要素** ツールで DOM ツリーを移動すると、ソースの順序を表すレンダリングされたページのセクションに数値オーバーレイ `header` が表示されます。 

:::image type="complex" source="../media/a11y-testing-source-order-viewer.msft.png" alt-text="ソース オーダー ビューアーをオンにすると、ページ上の数値オーバーレイとしてソース コード内の要素の順序が表示されます。" lightbox="../media/a11y-testing-source-order-viewer.msft.png":::
    ソース オーダー ビューアー **をオンに** すると、ページ上の数値オーバーレイとしてソース コード内の要素の順序が表示されます。
:::image-end:::

チュートリアルの詳細な手順については、「ソース オーダー ビューアーを [使用してキーボード サポートをテストする」に移動します](test-tab-key-source-order-viewer.md)。


## <a name="testing-contrast-of-text-colors-in-various-states"></a>さまざまな状態でのテキストの色のコントラストのテスト

検査 **ツールは** 、一度に 1 つの状態のアクセシビリティの問題を報告します。  まず、検査ツールを使用してページ要素の静的な状態のみを表示する制限について説明します。  次に、[スタイル] タブで **\:hov (Toggle Element State)** を選択して、ページ要素の他の状態を検査する方法 **について説明** します。

### <a name="checking-text-color-contrast-in-the-default-state"></a>既定の状態でテキストの色のコントラストを確認する

[問題] ツールの色コントラストの自動テスト**** に加えて、[検査] ツールを**** 使用して、個々のページ要素のコントラストが十分かどうかを確認することもできます。  コントラスト情報を使用できる場合は、[ **検査** ] オーバーレイにコントラスト比とチェック ボックス項目が表示されます。  緑色のチェック マーク アイコンは十分なコントラストを示し、黄色の警告アイコンは十分なコントラストを示します。

たとえば、サイドバーのナビゲーション メニューのリンクには十分なコントラストがありますが、[寄附金の状態] セクションの緑色の **犬** リスト **アイテムは** 表示されません。  十分なコントラストを持つ要素は、Inspect オーバーレイの警告によって **フラグが設定** されます。

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="[検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラストがあります。" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            [検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラスト **があります** 。 :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="十分なコントラストを持つ要素は、Inspect オーバーレイの警告によってフラグが設定されます。" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            十分なコントラストを持つ要素は、Inspect オーバーレイの警告によって **フラグが設定** されます。 :::image-end:::
    :::column-end:::
:::row-end:::

この方法 **で検査** ツールを使用しても、要素を完全にテストする必要があります。 ページ上の要素の状態が異なる場合があります。そのすべてがテストする必要があります。 たとえば、サイドバーのナビゲーション メニューの上にマウス ポインターを置くと、リンクの色を変更するアニメーションが表示されます。

:::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目" lightbox="../media/a11y-testing-hover.msft.png":::
    マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目
:::image-end:::

### <a name="verify-accessibility-of-all-states-of-elements-such-as-the-contrast-on-hover"></a>ホバーのコントラストなど、要素のすべての状態のアクセシビリティを確認する

DevTools を使用する場合は、検査ツールがすべての状態の情報を同時に表示し**** ないので、要素のすべての状態をシミュレートする必要があります。 この例では、[検査]**** ツールを使用している場合、スタイルの状態がトリガーされないので、サイドバー ナビゲーション メニューの [Cats] リンクの状態に到達して、状態のコントラスト比を分析できます。 `hover` **** `hover` `hover`  代わりに、[スタイル] タブの状態シミュレーションを使用して **、Cats** メニュー項目の状態を **シミュレートする必要** があります。

詳細なチュートリアル手順については、「要素のすべての状態 [のアクセシビリティを確認する」に移動します](test-inspect-states.md)。

[検査] **ツールを** オンにし、レンダリングされたページで、サイドバーのナビゲーション メニューで青い **Cats** リンクを選択します。  要素 **ツールが** 開き `a` 、DOM ツリーで要素が選択されます。  必要に応じて、DOM ツリーで、CSS の状態を持つ `hover` 要素に移動します。  この場合、要素 `a` には状態 `hover` があります。

:::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="要素ツールでホバー状態を持つ要素を検査する" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
    要素ツールでホバー状態を持つ要素を検査する
:::image-end:::

[スタイル] **タブ** で **、\:hov (要素の状態の切り替え) ボタンを選択** します。  次に **、[Force 要素の状態] チェック** ボックスを使用して、シミュレートする状態を選択します。

:::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="すべてのオプションを示す状態シミュレーション機能" lightbox="../media/a11y-testing-state-simulation.msft.png":::
    すべてのオプションを示す状態シミュレーション機能
:::image-end:::

**[\:hover] チェック ボックスを**オンにします。  DOM 要素の横に黄色のドットが表示され、DOM 要素にシミュレートされた状態が表示されます。  また、サイドバーナビゲーション メニューの **[Cats]** リンクが、マウス ポインターがカーソルを置いた場合と同様に、ページ内で強調表示されます。

:::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="ホバー状態をシミュレートする DevTools" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
    ホバー状態をシミュレートする DevTools
:::image-end:::

シミュレートされた状態を適用した後、もう一度****[検査] ツールを使用して、ユーザーが上にカーソルを置いたときに要素のコントラストを確認できます。  この場合、コントラストが十分に高くはない。

:::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="シミュレートされたホバー状態の要素のコントラストをテストする" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
    シミュレートされたホバー状態の要素のコントラストをテストする
:::image-end:::

状態シミュレーションは、ユーザーのニーズが異なっているかどうかを確認する良い方法です。  サイドバーのナビゲーション メニューでは、状態にコントラストの `:focus` 問題が発生しているのを検出できます。


## <a name="use-the-rendering-tool-to-test-accessibility-for-visual-impairment"></a>レンダリング ツールを使用して視覚障害のアクセシビリティをテストする

### <a name="check-contrast-issues-with-dark-theme-and-light-themes"></a>暗いテーマと明るいテーマのコントラストの問題を確認する

色のアクセシビリティに関するもう 1 つの考慮事項は、コントラストの問題をテストする必要があるテーマが異なる可能性がある点です。  ほとんどのオペレーティング システムには、暗いモードとライト モードがあります。  Web ページでは、CSS メディア クエリを使用して、これらの異なる設定に対応できます。

このデモ ページには、明るいテーマと暗いテーマがあります。  両方のテーマをオペレーティング システムを変更せずにテストするには、レンダリング ツールで [濃][DevToolsColorSchemeSimulation] 色または明るい配色のシミュレーションを **使用** します。  これまでのところ、この記事では、暗いテーマ設定を使用したオペレーティング システムを使用したデモ ページについて説明しました。  代わりにライト スキームをシミュレートし、ページを更新すると、[ **問題** ] ツールに 2 つの代わりに 6 つの色のコントラストの問題が表示されます。

チュートリアルの詳細な手順については、「濃いテーマと明るいテーマのコントラストの問題を確認 [する」に移動します](test-dark-mode.md)。


レンダリング ツールでライト テーマに切り替える **場合** は、次の項目に注意してください。

*  光のテーマが変更されたため、新しいコントラストの問題が検出されます。
*  ページの **[寄附状況** ] セクション全体は、ライト モードでは読み取りできません。

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="光のテーマが変更されたため、新しいコントラストの問題が検出されました" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
            光のテーマが変更されたため、新しいコントラストの問題が検出されました :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="光モードの場合にコントラストの問題としてフラグが設定された寄附状況アイテム" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
            光モードの場合にコントラストの問題としてフラグが設定された寄附状況アイテム :::image-end:::
    :::column-end:::
:::row-end:::


### <a name="verify-that-the-webpage-is-usable-by-people-with-color-blindness"></a>色覚を持つユーザーが Web ページを使用できると確認する

異なる寄付の状態では、資金の状態を区別する唯一の手段として、色 (赤、緑、黄色) が使用されます。  しかし、すべてのユーザーが意図した色でこれらの色を体験できるとは限らない。  DevTools の [ビジョン][DevToolsVisionDeficiencies] 不足エミュレーション機能を使用すると、異なるビジョンを持つユーザーがデザインをどのように認識するのかシミュレーションすることで、これが十分ではないと分かっています。
詳細なチュートリアル手順については、「ページが色覚を持つユーザーが使用できるページを確認する [」に移動します](test-color-blindness.md)。
:::image type="complex" source="../media/a11y-testing-simulating-protanopia.msft.png" alt-text="ページを protanopia (赤い色の失明) を持つユーザーとして表示すると、ページが表示されます" lightbox="../media/a11y-testing-simulating-protanopia.msft.png":::
    protanopia (赤い色の失明) を持つユーザーがページを表示する
:::image-end:::



### <a name="verify-that-the-webpage-is-usable-with-blurred-vision"></a>Web ページがぼやけたビジョンで使用できるのを確認する

レンダリング ツールのもう **1 つの興味深い** 機能は、ぼやけたビジョンをシミュレートできる点です。  [ビジョンの不**** 備をエミュレートする]**** ドロップダウン リストから [ぼやけたビジョン] オプションを選択すると、上部メニューのテキストのドロップ シャドウがメニュー項目を読みにくいのが分かっています。
詳細なチュートリアル手順については、「ページがぼやけたビジョンで使用できる」 [に移動します](test-blurred-vision.md)。

:::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="ぼやけたページをシミュレートすると、アクセシビリティの問題が発生する可能性があります" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
    ぼやけたページをシミュレートすると、アクセシビリティの問題が発生する可能性があります
:::image-end:::


### <a name="verify-that-the-page-is-usable-with-ui-animation-turned-off-reduced-motion"></a>ページが UI アニメーションをオフにした状態で使用できる (モーションの減少) を確認する

これらの日にオペレーティング システムが使用するもう 1 つの設定は、アニメーションをオフにする方法です。  アニメーションは、製品の使いやすさに役立ちますが、混乱から吐き気に至るまで、多くの問題を引き起こす可能性があります。 これは、オペレーティング システムでオフにしたユーザーに対して、製品がアニメーションを表示しない理由です。  CSS メディア クエリを使用すると、ユーザーがアニメーションを表示するかどうかを確認し、必要に応じてオフにできます。  また、暗いモードや明るいモードと同様に、DevTools を使用して縮小モーションを [シミュレートする方法があります][DevToolsReducedMotion]。

ここでのデモ ページでは、アニメーションをオフにすると、サイドバー ナビゲーション メニューの別の部分を選択すると、ページのスムーズなスクロールが停止します。  これは、メディア クエリで CSS でスムーズなスクロール設定をラップすることで実現されます。

:::image type="complex" source="../media/a11y-testing-simulating-reduced-motion.msft.png" alt-text="縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする" lightbox="../media/a11y-testing-simulating-reduced-motion.msft.png":::
    縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする
:::image-end:::

```css
@media (prefers-reduced-motion: no-preference) {
  html {
    scroll-behavior: smooth;
  }
}
```

この CSS メディア クエリは、条件付きで "スムーズスクロール" アニメーションを実行します。  ただし、トップ ナビゲーション バー、サイドバー ナビゲーション メニュー、**** その他のリンクのアニメーションは、ユーザーがアニメーションを表示したくない場合でも実行されます。 これらの他のアニメーションは、追加のメディア クエリを追加するなどの条件付きで実行する必要があります。

チュートリアルの詳細な手順については、「ページが UI アニメーションをオフにした状態で使用できる状態になっていることを確認 [する」に移動します](test-reduced-ui-motion.md)。


## <a name="what-to-do-next"></a>次に何をしますか?

製品のアクセシビリティの問題を確実にキャッチするために使用できるツールは、かなり多く取り上がっています。  このようなツールは、自動チェックや手動による詳細チェックから、さまざまな状態や環境のシミュレーションにまで及びます。  これらのツールは [、DevTools のアクセシビリティテスト機能に要約されています](reference.md)。  ユーザー補助の障壁の多くは対話型の使用中にのみ表示されるので、自動化されたツールは製品内のすべての問題を見つけ出すことはありません。

これらのツールはいずれも、製品の適切なテストラウンドを支援技術を使用するユーザーに置き換え、必要なすべてのテストを確認する計画に従う必要はありません。 アクセシビリティ 機能の評価機能を[使用][AccessibilityInsightsAssessment][インサイト。][AccessibilityInsights]  次のような追加のチェックを実行する必要がある場合があります。

* ズームイン時のテスト。
* スクリーン リーダーによるテスト。
* 音声認識によるテスト。
* ハイ コントラスト モードでのテスト。

Web 製品を改善するために何を行うのかを確認するもう 1 つの方法は、webhint 拡張機能を使用して[webhint][WebhintForCode]拡張機能を使用Visual Studio Code。  この拡張機能は、ソース コードで容易に検出できるアクセシビリティの問題にフラグを設定し、それらを修正する方法に関する分析情報を提供します。

:::image type="complex" source="../media/a11y-testing-webhint-in-vs-code.msft.png" alt-text="Webhint Visual Studio Code HTML 要素の下線を引き、問題の説明を表示してアクセシビリティの問題を表示する" lightbox="../media/a11y-testing-webhint-in-vs-code.msft.png":::
    Webhint Visual Studio Code HTML 要素の下線を引き、問題の説明を表示してアクセシビリティの問題を表示する
:::image-end:::

DevTools の新しいアクセシビリティ機能に常に取り組み続け中です。  不足している何かがある場合は、メッセージを送信し、何が可能かを教えて下さい。


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]


<!-- links -->
[DevToolsMediaQueries]: ../device-mode/index.md#show-media-queries "メディア クエリの表示 - DevTools アプリケーションでモバイル Microsoft Edgeをエミュレート|Microsoft Docs"
[DevToolsDeviceModeIndex]: ../device-mode/index.md "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "暗いまたは明るい配色のシミュレーション |Microsoft Docs"
[DevToolsIssuesTool]: ../issues/index.md "[問題] ツール を使用して問題を見つけて修正|Microsoft Docs"
[DevToolsReducedMotion]: ./reduced-motion-simulation.md "モーション シミュレーションの|Microsoft Docs"
[DevToolsVisionDeficiencies]: ./emulate-vision-deficiencies.md "ビジョンの欠陥をエミュレート|Microsoft Docs"
<!-- links into test-issues-tool.md -->
[DevToolsAccessibilityTestIssuesToolViewAccSection]: test-issues-tool.md#view-the-accessibility-section-of-the-issues-tool "[問題] ツールの [アクセシビリティ] セクションを表示する - Web ページでアクセシビリティの問題を自動的にテスト|Microsoft Docs"
[DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]: test-issues-tool.md#verify-that-input-fields-have-labels "入力フィールドにラベルが含まれていますを確認する - ユーザー補助の問題について Web ページを自動的にテスト|Microsoft Docs" 
[DevtoolsAccessibilityTestIssuesToolCheckAltText]: test-issues-tool.md#verify-that-images-have-alt-text "画像に代替テキストが含まれています - Web ページでアクセシビリティの問題を自動的にテスト|Microsoft Docs "
[DevtoolsAccessibilityTestIssuesToolCheckContrast]: test-issues-tool.md#verify-that-text-colors-have-enough-contrast "テキストの色のコントラストが十分に高い - Web ページでアクセシビリティの問題が自動的にテスト|Microsoft Docs"
<!-- links into test-inspect-tool.md -->
[DevtoolsAccessibilityTestInspectToolColorHighlighting]: test-inspect-tool.md#identify-nested-regions-using-color-highlighting "色の強調表示を使用して入れ子になった領域を特定する - [検査] ツールを使用して、Web ページの上にマウス ポインターを置いてアクセシビリティの問題を検出|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolIndivElems]: test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support "個々の要素でテキストのコントラスト、スクリーン リーダー テキスト、キーボードのサポートを確認する - [検査] ツールを使用して、Web ページの上にマウス ポインターを置いてアクセシビリティの問題を検出|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolDomCss]: test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css "[検査] ツールを使用して Web ページにカーソルを合わせると、DOM と CSS が強調表示されます 。 [検査] ツールを使用して、Web ページの上にマウス ポインターを置いてアクセシビリティの問題を検出|Microsoft Docs"
<!-- external links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "コントラスト比|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web コンテンツ アクセシビリティ ガイドライン |W3C"
[AccessibilityInsightsAssessment]: https://accessibilityinsights.io/docs/en/web/getstarted/assessment/ "Web サービスのアクセシビリティ インサイト評価|アクセシビリティ インサイト"
[AccessibilityInsights]: https://accessibilityinsights.io "アクセシビリティ インサイト"
[Lighthouse]: https://developers.google.com/web/tools/lighthouse/ "ライトハウス |Google"
[WebhintForCode]:https://aka.ms/webhint4code "webhint |Visual StudioMarketplace"
