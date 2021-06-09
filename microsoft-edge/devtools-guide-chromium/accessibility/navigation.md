---
description: スクリーン リーダーのような支援テクノロジMicrosoft Edge DevTools のナビゲーションに関するガイド。
title: 支援Microsoft Edge DevTools のナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2cb57a8ea1ea34506b4698d80ae0981d8716f3d2
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597101"
---
<!-- Copyright Rob Dodson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="navigate-microsoft-edge-devtools-with-assistive-technology"></a>支援Microsoft Edge DevTools のナビゲーション  

この記事では、主にスクリーン リーダーなどの支援テクノロジに依存しているユーザーが[DevTools][MicrosoftEdgeDevtoolsMain]を使用Microsoft Edge役立ちます。  DevTools は、ブラウザーに組み込Microsoft Edgeです。  

Web ページのアクセシビリティの向上に関連する [DevTools 機能については、「DevTools][DevtoolsAccessibilityReference] のアクセシビリティ テスト機能」および [「DevTools](accessibility-testing-in-devtools.md)を使用したアクセシビリティ テストの概要」を参照してください。

DevTools のアクセシビリティは、進行中の作業です。  一部のツールとタブは、他のツールよりも支援テクノロジの方が優れた機能を提供します。  このガイドでは、最もアクセスしやすいツールとタブについて説明し、途中で発生する可能性のある特定の問題について説明します。  

## <a name="overview"></a>概要  

DevTools は、一連のツールに分かれています。  (コマンド メニュー **内では**、ツールはパネルと _呼ばれます_。) ツールは、メイン ツールバーと引き出しツール バーの [ARIA][W3CWaiAriaTablist] タブリストに整理されています。

ツールの例を次に示します。

*   要素 **ツール** を使用すると、[DOM ノードの表示と変更][DevtoolsDomIndexNavigateDomTreeKeyboard] または CSS を使用 [できます][DevtoolsCssIndex]。  
*   コンソール **ツールを** 使用すると、JavaScript ログとライブ編集オブジェクトを読み取りできます。  詳細については、「コンソールを使用 [する」に移動します][DevtoolsConsoleIndex]。

各ツールには、1 つ以上のタブセットがあります。  たとえば、要素ツール**には**、スタイル、イベント リスナー、アクセシビリティ**などの**一**** 連のタブ**が含まれています**。

## <a name="keyboard-shortcuts"></a>キーボード ショートカット  

[DevTools キーボード ショートカット リファレンス][DevtoolsShortcuts] は便利なチートシートです。  異なるツールを探索する場合は、必ずブックマークを作成して参照してください。

## <a name="open-devtools"></a>DevTools を開く  

開始するには、[Open Microsoft Edge DevTools][DevtoolsOpen] に移動します。  キーボード ショートカットまたはメニュー項目を使用して DevTools を開く方法は多数あります。  

## <a name="navigate-between-tools"></a>ツール間の移動

### <a name="navigate-by-keyboard"></a>キーボードによる移動  

*   DevTools を開いた `Control` + `]` 後、\(Windows、Linux\) または `Command` + \(macOS\) を選択して、メイン ツールバーの次のツールに `]` フォーカスを移動します。
*   `Control` + `[` \(Windows、Linux\) または `Command` + \(macOS\) を選択して、メイン ツールバーの前の `[` ツールにフォーカスを移動します。
*   メイン ツールバーまたはドロワー ツールバーのタブにフォーカスが移動するまで、または繰り返し選択してから、矢印キーを使用してツール `Tab` `Shift` + `Tab` 間を移動します。

**既知の問題**  

*   [コンソール] ツールや****[**** パフォーマンス] ツールなどの一部のツールは、ツールが選択された時点でツールのコンテンツ領域にフォーカスを移動する場合があります。  これにより、矢印キーによる移動が困難になる場合があります。  
*   選択したツールの名前は発表されますが、ツールでフォーカスされたコンテンツを発表した後にのみ発表されます。  この一連のアナウンスにより、ツールの名前を簡単に見逃す可能性があります。

### <a name="navigate-by-command-menu"></a>[コマンド] メニューで移動する  

特定のツールを選択するには、コマンド メニュー [を使用します][DevtoolsCommandMenuIndex]。  コマンド メニューでは、ツールをパネルと呼 _びます_。

1.  DevTools を開いた後 `Control` + `Shift` + `P` 、\(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを**開きます**。  
    コマンド **メニューは** 、ファジー検索オートコンプリート コンボボックスです。  
1.  パネル (ツール) の名前を入力し、キーボードで正しいオプション `Down Arrow` に移動します。  
1.  コマンド `Enter` を実行する場合に選択します。  

要素ツールを **開く** 方法:

1.  **コマンド メニュー** を開きます。  
1.  次に `E` 入力 `L` します。  [ **パネル] >要素の表示** ] オプションが選択されています。  
1.  `Enter` を選択します。  

ツールを開く方法は、ツールのコンテンツ領域にフォーカスを置きます。  Elements ツールの場合、 **フォーカス** は DOM ツリーに **移動します**。

## <a name="elements-tool"></a>要素ツール

### <a name="inspect-an-element-on-the-page"></a>ページ上の要素を検査する  

1.  スクリーン リーダーのカーソルを使用して、検査する要素に移動します。  
1.  要素を右クリックして、コンテキスト メニューを開きます。  
1.  [検査] **オプションを選択** します。  この [要素] ツールを開き、DOM ツリー内の要素に焦点を当て、[DevtoolsDomIndexViewDomNodes] を選択します。  

**DOM ツリーは** [ARIA ツリーとしてレイアウトされます][W3CWaiAriaTree]。  例については、[キーボードを使用して **DOM ツリー** を移動する][DevtoolsDomIndexNavigateDomTreeKeyboard]に移動します。  

### <a name="copy-the-code-for-an-element-in-the-dom-tree"></a>DOM ツリー内の要素のコードをコピーする  

1.  **DOM**ツリーのノードにフォーカスを合わせると、ノードにカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。  
1.  [コピー] **オプションを展開** します。  
1.  [外部 **HTML のコピー] を選択します**。  

**既知の問題**  

*   **多くの場合、copy outerHTML** は現在のノードを選択するのではなく、親ノードを選択します。  ただし、要素の内容はコピーされた outerHTML に残っている必要があります。  

### <a name="modify-the-attributes-of-an-element-in-the-dom-tree"></a>DOM ツリー内の要素の属性を変更する  

*   **DOM**ツリーのノードにフォーカスを置き、編集 `Enter` 可能にする場合に選択します。  
*   属性値 `Tab` 間を移動する場合に選択します。  "スペース" と聞くと、空のテキスト入力の内側に新しい属性値を入力できます。  
*   `Control` + `Enter` \(Windows、Linux\) または `Command` + \(macOS\) を選択して変更を受け入れ、要素の内容 `Enter` 全体を確認します。  

**既知の問題**  

*   テキスト入力を入力すると、フィードバックは得かねない。  入力ミスを行い、矢印キーを使用して入力を確認すると、フィードバックも得かねない。  作業を確認する最も簡単な方法は、変更を受け入れてから、発表される要素全体をリッスンする方法です。  

### <a name="edit-the-html-of-an-element-in-the-dom-tree"></a>DOM ツリーで要素の HTML を編集する  

*   **DOM**ツリーのノードにフォーカスを置き、編集 `Enter` 可能にする場合に選択します。  
*   属性値 `Tab` 間を移動する場合に選択します。  たとえば、要素の名前が聞こえると、テキスト入力の内部にいて、要素の種類 `h2` が変更される可能性があります。  
*   `Control` + `Enter` \(Windows Linux\) または `Command` + `Enter` \(macOS\) を選択して変更を受け入れる。  

たとえば `h3` `Control` + `Enter` 、\(Windows、Linux\) または `Command` + `Enter` \(macOS\) を入力して選択すると、要素の開始タグと終了タグが `h3` 変更されます。  

## <a name="tabs-in-the-elements-tool"></a>[要素] ツールのタブ

要素 **ツール** には、要素に適用される CSS やアクセシビリティ ツリー内の関連する場所など、その他のタブが含まれています。  

*   DOM ツリーのノードにフォーカスがある場合 **は、[** スタイル] タブが選択されているという声 `Tab` **が聞こえる** まで選択します。  
*   その他の `Right Arrow` 使用可能なタブを表示するには、次のコマンドを使用します。

**DOM ツリーは**属性を持つ要素をフォーカス可能なリンクに変換します。そのため、[スタイル] ウィンドウに移動するには、複数の要素 `href` を選択 `Tab` する**必要があります**。  

**既知の問題**  

**[DOM ブレークポイント] タブと** **[プロパティ] タブ**はキーボードアクセス可能ではありません。  

### <a name="styles-pane"></a>[スタイル] ウィンドウ  

[スタイル **] ウィンドウで**、スタイルのフィルター処理、要素の状態 \(:active、:focus\など) の切り替え、クラスの切り替え、および新しいクラスの追加のコントロールを検索します。 [][MDNActive] [][MDNFocus]  また、DOM ツリーでフォーカスされている要素に現在適用されているスタイルを探索および変更するための強力なスタイル検査ツール **も用意されています**。  

[スタイル] ウィンドウについて理解**** する重要な概念は、DOM ツリーで現在選択されているノードのスタイルのみを**表示する点です**。  たとえば、ノードのスタイルの検査が完了し、ノードのスタイルを確認 `<header>` すると `<footer>` します。  これを行うには、まず DOM ツリーで `<footer>` ノードを選択する **必要があります**。  Inspect ワークフローを使用して[](#inspect-an-element-on-the-page)、DOM ツリーに焦点を当てたノード `footer` \(フッター\内のリンクなど) の一般的な近傍にあるノードを検査し、**** キーボードを使用して目的の正確なノードに移動する方が速い場合があります。  

#### <a name="navigate-the-styles-pane"></a>[スタイル] ウィンドウを移動する  

すべてのスタイル ツールは、何通りか別の方法で [**** スタイル] ウィンドウに接続されます。このツールの専門家になるのは、まず意味があります。  

*   [スタイル] ウィンドウに **フォーカスを置** いて、フォーカス `Tab` を内側に移動し、コンテンツを確認します。  
*   最初 `Tab` のスタイルがアクティブになるまで選択します。  スクリーン リーダーを使用している場合、この最初のスタイルはとして発表されます `element.style {}` 。  
*   スタイル `Down Arrow` の一覧を特定の順序で移動する場合に選択します。  スクリーン リーダーは、CSS ファイルの名前、スタイルが表示される行番号、およびスタイルの名前から始まる各スタイルをアナウンスします。  例: `main.css:233 .card__img {}`。  
*   スタイル `Enter` の詳細を調べている場合に選択します。  フォーカスは、スタイル名の編集可能なバージョンから始まります。  
*   各 `Tab` CSS プロパティの編集可能なバージョンと対応する値の間を移動する場合に選択します。  各スタイル ブロックの末尾には、空白の編集可能なテキスト フィールドが表示され、追加の CSS プロパティを追加できます。  
*   引き続き選択してスタイルの一覧を移動するか、モードを終了して矢印キーでナビゲーション `Tab` `Escape` に戻ります。  

追加のショートカットについては、[スタイル ウィンドウ キーボード リファレンス][DevtoolsShortcutsStylesPaneKeyboard]に移動します。  

**既知の問題**  

*   [編集可能なテキストの **フィルター]** フィールドを使用すると、スタイルの一覧を移動できなくなりました。  

#### <a name="toggle-element-state"></a>要素の状態を切り替える  

要素の状態を切り替えるには、次のように `:active` します `:focus` 。  

1.  [スタイル] ウィンドウ **に移動** し、[要素 `Tab` の状態の切り替え] ボタンがフォーカスを **持つまで** 選択します。  
1.  要素 `Enter` の状態のコレクションを展開する場合に選択します。  要素の状態は、チェック ボックスのグループとして表示されます。  
1.  最初 `Tab` の状態がフォーカスを `:active` 持つまで選択します。  
1.  有効 `Space` にする場合に選択します。  DOM ツリーで現在選択されている要素にスタイルがある場合は `:active` 、そのスタイルが適用されます。  
1.  ホールド `Tab` して、使用可能なすべての状態を確認します。  

#### <a name="add-an-existing-class"></a>既存のクラスを追加する  

[要素の状態の **切り替え] ボタン** の隣には、[ **要素クラス] ボタン** があります。  フォーカスを移動するには、を選択 `Tab` して選択します `Enter` 。  [新しいクラスの追加] というラベルの付いた編集テキスト フィールド **にフォーカスが移動します**。  

[ **要素クラス]** ボタンは、主に要素に既存のクラスを追加するために使用されます。  たとえば、スタイルシートにヘルパー クラスという名前のヘルパー クラスが含まれている場合は、編集テキスト フィールドの内部を選択して、クラスの候補リストを表示し、 を使用して候補を `.clearfix` `.` `Down Arrow` 検索 `.clearfix` できます。  または、自分でクラス名を入力し、適用 `Enter` を選択します。  

#### <a name="add-a-new-style-rule"></a>新しいスタイル ルールを追加する  

[要素クラス] **ボタンの隣** には、[新しいスタイル **ルール] ボタン** があります。  フォーカスを移動するには、を選択 `Tab` して選択します `Enter` 。  フォーカスは、スタイル インスペクター内の編集可能なテキスト フィールドに移動します。  フィールドの最初のテキストコンテンツは **、DOM**ツリーで選択されている要素のタグ名です。  
このフィールドに任意のクラス名を入力し、CSS プロパティを割り当 `Tab` てる場合に選択できます。  

### <a name="computed-tab"></a>[計算] タブ  

[計算] タブに **フォーカスを置** いて、フォーカス `Tab` を内部に移動し、コンテンツを探索する場合に選択します。  [計算 **] タブ** には、特定の順序で要素に実際に適用される CSS プロパティを確認するコントロールがあります。  

<!--todo: add Computed tab section when available  -->  

#### <a name="explore-all-computed-styles"></a>すべての計算スタイルを見る  

計算 `Tab` されたスタイルのコレクションに到達するまで選択します。  これらは ARIA ツリー [として表示されます][W3CWaiAriaTree]。  リスト ボックスを展開すると、計算されたスタイルを適用している CSS セレクターが表示されます。  これらのセレクターは、固有の構成で構成されます。  スクリーン リーダーは、計算された値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、およびセレクターの行番号をアナウンスします。  

**既知の問題**  

*   [フィルター] テキスト **フィールドを** 使用すると、スタイルを検査できなくなりました。  

### <a name="event-listeners-tab"></a>[イベント リスナー] タブ  

要素に適用されるイベント リスナーを調べたい場合は、[要素****] ツールを選択し****、[イベント リスナー] タブ ([スタイル] タブでグループ化)**を選択**します。

#### <a name="explore-event-listeners"></a>イベント リスナーの探索  

イベント リスナーは [ARIA ツリーとして表示されます][W3CWaiAriaTree]。  矢印キーを使用して移動できます。  スクリーン リーダーは、イベント リスナーが接続されている DOM オブジェクトの名前と、イベント リスナーが定義されているファイル名と行番号をアナウンスします。  

### <a name="accessibility-tab"></a>[アクセシビリティ] タブ

要素ツール `Tab` の [アクセシビリティ]**** タブ内で移動するキーを**選択**します。

[ **アクセシビリティ] タブ** は、[スタイル] タブ **の近** くに表示されます。[アクセシビリティ] タブには、アクセシビリティ ツリー、要素に適用される ARIA 属性、および計算されたアクセシビリティ プロパティを探索するコントロールがあります。  詳細については、[アクセシビリティ] タブを [使用してアクセシビリティをテストするに移動します][DevtoolsAccessibilityTab]。

#### <a name="accessibility-tree"></a>アクセシビリティ ツリー  

アクセシビリティ **ツリーは ARIA** ツリーとして表示され、 [各][W3CWaiAriaTree] ツリーは DOM 内の `treeitem` 要素に対応します。  ツリーは、選択したノードの計算された役割をアナウンスします。  ツリー内の `div` `span` "GenericContainer" のような汎用的な要素が発表されます。  矢印キーを使用してツリーを走査し、親子関係を探索します。  

**既知の問題**  

*   [アクセシビリティ][タブで使用][W3CWaiAriaTree]される**** ARIA ツリーの種類は、VoiceOver のような macOS スクリーン リーダー Microsoft Edgeで適切に公開されない場合があります。  この問題[Chromium進捗#868480][ChromiumIssues868480]通知を受け取る場合は、この問題を購読してください。  
*   **[ARIA 属性**]**** セクションと [計算されたプロパティ] セクションのそれぞれは[ARIA][W3CWaiAriaTree]ツリーとしてマークされますが、それぞれが現在フォーカス管理を行っているのではなく、キーボード操作可能ではありません。  

## <a name="lighthouse-tool"></a>ライトハウス ツール

**ライト** ハウスはサイトに対して一連のテストを実行し、パフォーマンス、アクセシビリティ、SEO、その他の多くのカテゴリに関連する一般的な問題を確認します。  

### <a name="configure-and-generate-a-report"></a>レポートの構成と生成

1.  DevTools **で** ライトハウス ツールが最初に開かれると、[レポートの生成] ボタンにフォーカス **が置** きます。  既定では、フォームは、シミュレートされた 3G 接続でモバイル エミュレーションを使用してすべてのカテゴリのレポートを実行するように構成されています。  
1.  レポートの設定を変更するには、ライトハウスの設定にフォーカスを当てたり、ブラウズ `Shift` + `Tab` モードで戻って移動したりします。 ****  
1.  レポートを実行する準備ができたら、[レポートの生成] ボタンに戻 **り、** を選択します `Enter` 。  
1.  フォーカスは、監査を終了できる **[キャンセル** ] ボタンを使用してモーダル ウィンドウに移動します。  監査が実行され、ページが複数回更新されると、一連の耳鳴り音が聞こえる場合があります。  

**既知の問題**  

*   構成フォームの異なるセクションは、現在要素でマーク `fieldset` 付けされていない。  参照モードで移動して、各セクションに関連付けられているコントロールを把握する方が簡単な場合があります。  
*   監査の実行が完了すると、耳コンやライブ領域のアナウンスはありません。  通常、監査には約 30 秒かかっています。その後、結果に移動できる必要があります。  ブラウズ モードを使用すると、結果に最も簡単にアクセスできます。  

### <a name="navigate-the-lighthouse-report"></a>ライトハウス レポートを移動する  

ライトハウス レポートは、各監査カテゴリに対応するセクションに編成されます。  レポートが開き、各カテゴリのスコアの一覧が表示されます。  これらのスコアは、関連するセクションにスキップするために使用できるリンクです。  各セクション内には、渡された監査または失敗した監査に関連する情報を含む拡張可能 `details` な要素があります。  既定では、失敗した監査だけが表示されます。  各セクションは、渡された `details` 監査のすべてが含まれる最終的な要素で終わります。  

新しい監査を実行するには、レポート `Shift` + `Tab` を終了し、[レポートの生成] ボタン**を選択**します。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"  
[DevtoolsAccessibilityTab]: accessibility-tab.md "[アクセシビリティ] タブを使用してアクセシビリティをテスト|Microsoft Docs"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "[DevTools コマンド メニュー] Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要 | Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "はじめにCSS の表示と変更を使用|Microsoft Docs"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md#view-dom-nodes "View DOM ノード - DOM ノードの表示と変更の|Microsoft Docs"  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "キーボードを使用して DOM ツリーを移動する - DOM ツリーの表示と変更の|Microsoft Docs"  
[DevtoolsOpen]: ../open/index.md "Open Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts/index.md#styles-panel-keyboard-shortcuts "Styles panel keyboard shortcuts - Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "問題 868480 - Mac アクセシビリティで ARIA ツリーをテーブルとして公開する"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新しい問題 - MicrosoftDocs/edge-developer |GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ":active |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ":focus |MDN"  

[MonorailChromiumIssues]: https://crbug.com "問題 - クロム - モノレール"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (role) - アクセス可能なリッチ インターネット アプリケーション (WAI-ARIA) 1.1 |W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "tree (role) - アクセス可能なリッチ インターネット アプリケーション (WAI-ARIA) 1.1 |W3C"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) つかり [、Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[RobDodson]: https://developers.google.com/web/resources/contributors#rob-dodson  
