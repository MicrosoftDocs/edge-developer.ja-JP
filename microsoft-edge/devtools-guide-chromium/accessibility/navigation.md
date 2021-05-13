---
description: スクリーン リーダーのような支援テクノロジMicrosoft Edge DevTools のナビゲーションに関するガイド。
title: 支援Microsoft Edge DevTools のナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cf2742dfb08ee482b26fe43417b7454e5b6ff809
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564582"
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

次の記事は、主にスクリーン リーダーのような支援テクノロジに依存しているユーザーが DevTools にアクセスして使用Microsoft Edge[を目的とします][MicrosoftEdgeDevtoolsMain]。  [Microsoft Edge DevTools は][MicrosoftEdgeDevtoolsMain]、ブラウザーに組み込Microsoft Edgeです。  Web ページのアクセシビリティの向上に関連する DevTools 機能を探している場合は、[アクセシビリティ リファレンス] [に移動します][DevtoolsAccessibilityReference]。  

DevTools のアクセシビリティは、進行中の作業です。  一部のパネルとタブは、他のパネルよりも支援技術に優れた機能を備えます。  このガイドでは、最もアクセスしやすいパネルについて説明し、途中で発生する可能性のある特定の問題について説明します。  

## <a name="overview"></a>概要  

開始する前に、DevTools UI の構造化方法のメンタル モデルを作成するのに役立ちます。  DevTools は、ARIA タブリストに編成された一連の [パネルに分かれています][W3CWaiAriaTablist]。  

以下に例を示します。  

*   要素 **ツール** を使用すると、[DOM ノードの表示と変更][DevtoolsDomIndexNavigateDomTreeKeyboard] または CSS を使用 [できます][DevtoolsCssIndex]。  
*   コンソール [パネルでは、JavaScript][DevtoolsConsoleIndex] ログとライブ編集オブジェクトを読み取りできます。  

各パネルのコンテンツ領域内には、多くの場合、ドキュメント内のタブまたはウィンドウと呼ばれるさまざまなツールがあります。  
たとえば **、Elements** ツールには、イベント リスナー、アクセシビリティ ツリーなど、その他のタブが含まれています。  タブとウィンドウの違いは、やや任意です。  1 つの用語または他の用語を確認する唯一の理由は、DevTools の公式ドキュメントの残りの部分との整合性を維持する方法です。  

## <a name="keyboard-shortcuts"></a>キーボード ショートカット  

[DevTools キーボード ショートカット リファレンス][DevtoolsShortcuts] は役に立つチートシートです。  異なるパネルを探索する場合は、必ずブックマークを作成し、参照してください。  

## <a name="open-devtools"></a>DevTools を開く  

開始するには、[Open Microsoft Edge DevTools][DevtoolsOpen] に移動します。  キーボード ショートカットまたはメニュー項目を使用して DevTools を開く方法は多数あります。  

## <a name="navigate-between-panels"></a>パネル間を移動する  

### <a name="navigate-by-keyboard"></a>キーボードによる移動  

*   DevTools を開いた後 `Control` + `]` 、\(Windows、Linux\) または \(macOS\) を選択して、次のパネル `Command` + `]` にフォーカスを設定します。  
*   `Control` + `[` 前のパネルにフォーカスWindows \(Windows Linux\) または `Command` + `[` \(macOS\) を選択します。  
*   パネルの `Shift` + `Tab` [ARIA][W3CWaiAriaTablist]タブリストにフォーカスを移動し、矢印キーを使用してパネルを変更することもできますが、前述のショートカットを使用する方が速い場合があります。  

**既知の問題**  

*   [コンソール] ツールや [ **パフォーマンス]** ツールなどの一部の **パネルでは、** 各パネルがアクティブ化されるとすぐに、パネルコンテンツ領域にフォーカスが移動する場合があります。  これにより、矢印キーによる移動が困難になる場合があります。  
*   選択したパネルの名前は発表されますが、パネル内のフォーカスされたコンテンツを読み取った後にのみ発表されます。  これにより、見逃しが非常に簡単になります。  

### <a name="navigate-by-command-menu"></a>[コマンド] メニューで移動する  

特定のパネルをフォーカスするには、コマンド メニュー [を使用します][DevtoolsCommandMenuIndex]。  

1.  DevTools を開いた後 `Control` + `Shift` + `P` 、\(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを**開きます**。  
    コマンド **メニューは** 、あいまい検索オートコンプリート コンボ ボックスです。  
1.  開くパネルの名前を入力し、キーボードで正しいオプション `Down Arrow` に移動します。  
1.  コマンド `Enter` を実行する場合に選択します。  

次のアクションを実行して、[要素] ツール **を開** きます。  

1.  **コマンド メニュー** を開きます。  
1.  次に `E` 入力 `L` します。  [ **パネル] >要素の表示** ] オプションが選択されています。  
1.  パネル `Enter` を開くコマンドを実行する場合に選択します。  

この方法でパネルを開き、パネルの内容にフォーカスを当てる。  Elements ツールの場合、 **フォーカス** は DOM ツリーに **移動します**。  

## <a name="elements-panel"></a>[要素] パネル  

### <a name="inspect-an-element-on-the-page"></a>ページ上の要素を検査する  

1.  スクリーン リーダーのカーソルを使用して検査する要素に移動します。  
1.  要素のマウスを使用して右クリックをシミュレートし、コンテキスト メニューを開きます。  
1.  [検査] **オプションを選択** します。  この [要素] パネルが開き、DOM ツリー内の要素に焦点を当て、[DevtoolsDomIndexViewDomNodes] になります。  

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

## <a name="elements-tool-panels"></a>要素ツール パネル  

要素 **ツール** には、要素に適用される CSS やアクセシビリティ ツリー内の関連する場所など、その他のタブが含まれています。  

*   DOM ツリーのノードにフォーカスがある場合 **は、[** スタイル] ウィンドウが選択されているという `Tab` 音 **がするまで** 選択します。  
*   その他の `Right Arrow` 使用可能なタブを表示するには、次のコマンドを使用します。  

**DOM ツリーは**属性を持つ要素をフォーカス可能なリンクに変換します。そのため、[スタイル] ウィンドウに移動するには、複数の要素 `href` を選択 `Tab` する**必要があります**。  

**既知の問題**  

**[DOM ブレークポイント] タブと** **[プロパティ] タブ**はキーボードにアクセスすることはできません。  

### <a name="styles-pane"></a>[スタイル] ウィンドウ  

[スタイル **] ウィンドウで**、スタイルのフィルター処理、要素の状態 \(:active、:focus\など) の切り替え、クラスの切り替え、および新しいクラスの追加のコントロールを検索します。 [][MDNActive] [][MDNFocus]  また、DOM ツリーでフォーカスされている要素に現在適用されているスタイルを探索および変更するための強力なスタイル検査ツール **も用意されています**。  

[スタイル] ウィンドウについて理解**** する重要な概念は、DOM ツリーで現在選択されているノードのスタイルのみを**表示する点です**。  たとえば、ノードのスタイルの検査が完了し、ノードのスタイルを確認 `<header>` すると `<footer>` します。  これを行うには、まず DOM ツリーで `<footer>` ノードを選択する **必要があります**。  Inspect ワークフローを使用して[](#inspect-an-element-on-the-page)、DOM ツリーに焦点を当てたノード `footer` \(フッター\内のリンクなど) の一般的な近傍にあるノードを検査し、**** キーボードを使用して目的の正確なノードに移動する方が速い場合があります。  

#### <a name="navigate-the-styles-pane"></a>[スタイル] ウィンドウを移動する  

すべてのスタイル ツールは、何通りか別の方法で [**** スタイル] ウィンドウに接続されます。このツールの専門家になるのは、まず意味があります。  

*   [スタイル] ウィンドウに **フォーカスを置** いて、フォーカス `Tab` を内側に移動し、コンテンツを確認します。  
*   最初 `Tab` のスタイルがアクティブになるまで選択します。  スクリーン リーダーを使用している場合、この最初のスタイルはとして発表されます `element.style {}` 。  
*   スタイル `Down Arrow` の一覧を特定の順序で移動する場合に選択します。  スクリーン リーダーは、CSS ファイルの名前、スタイルが表示される行番号、およびスタイルの名前から始まる各スタイルをアナウンスします。  例: `main.css:233 .card__img {}`。  
*   スタイル `Enter` の詳細を調べている場合に選択します。  フォーカスは、スタイル名の編集可能なバージョンから始まります。  
*   各 `Tab` CSS プロパティの編集可能なバージョンと対応する値の間を移動する場合に選択します。  各スタイル ブロックの最後には、空白の編集可能なテキスト フィールドが表示され、追加の CSS プロパティを追加するために使用できます。  
*   引き続き選択してスタイルの一覧を移動するか、モードを終了して矢印キーによるナビゲーション `Tab` `Escape` に戻ります。  

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

[要素の状態の **切り替え] ボタン** の隣には、[ **要素クラス] ボタン** があります。  フォーカスを移動するには、を選択して `Tab` 選択します `Enter` 。  [新しいクラスの追加] というラベルの付いた編集テキスト フィールド **にフォーカスが移動します**。  

[ **要素クラス]** ボタンは、主に要素に既存のクラスを追加するために使用されます。  たとえば、スタイルシートにという名前のヘルパー クラスが含まれている場合は、編集テキスト フィールドの内側を選択して、クラスの候補リストを表示し、 を使用して候補を `.clearfix` `.` `Down Arrow` 検索 `.clearfix` できます。  または、自分でクラス名を入力し、適用 `Enter` を選択します。  

#### <a name="add-a-new-style-rule"></a>新しいスタイル ルールを追加する  

[要素クラス] **ボタンの隣** には、[新しいスタイル **ルール] ボタン** があります。  フォーカスを移動するには、を選択して `Tab` 選択します `Enter` 。  フォーカスは、スタイル インスペクター内の編集可能なテキスト フィールドに移動します。  フィールドの最初のテキストコンテンツは **、DOM**ツリーで選択されている要素のタグ名です。  
このフィールドに任意のクラス名を入力し、CSS プロパティを割り当 `Tab` てる場合に選択できます。  

### <a name="computed-tab"></a>[計算] タブ  

[計算] タブに **フォーカスを置** いて、フォーカス `Tab` を内部に移動し、コンテンツを探索する場合に選択します。  [計算 **] タブ** には、特定の順序で要素に実際に適用される CSS プロパティを確認するコントロールがあります。  

<!--todo: add computed tab section when available  -->  

#### <a name="explore-all-computed-styles"></a>すべての計算スタイルを見る  

計算 `Tab` されたスタイルのコレクションに到達するまで選択します。  これらは ARIA ツリー [として表示されます][W3CWaiAriaTree]。  リスト ボックスを展開すると、計算されたスタイルを適用している CSS セレクターが表示されます。  これらのセレクターは、固有の構成で構成されます。  スクリーン リーダーは、計算された値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、およびセレクターの行番号をアナウンスします。  

**既知の問題**  

*   [フィルター] テキスト **フィールドを** 使用すると、スタイルを検査できなくなりました。  

### <a name="event-listeners-tab"></a>[イベント リスナー] タブ  

要素ツール **内から** 、[イベント リスナー] タブを使用して、要素に適用されるイベント **リスナーを検査** できます。 [スタイル] パネルに **フォーカスを置** き、[イベント リスナー] `Right Arrow` パネル **に移動します** 。  

#### <a name="explore-event-listeners"></a>イベント リスナーの探索  

イベント リスナーは [ARIA ツリーとして表示されます][W3CWaiAriaTree]。  矢印キーを使用して移動できます。  スクリーン リーダーは、イベント リスナーが接続されている DOM オブジェクトの名前と、イベント リスナーが定義されているファイル名と行番号をアナウンスします。  

### <a name="accessibility-pane"></a>アクセシビリティ ウィンドウ  

[アクセシビリティ] ウィンドウに **フォーカスを置いて** 、フォーカス `Tab` を内部に移動し、コンテンツを探索する場合に選択します。  [アクセシビリティ [] ウィンドウには][DevtoolsAccessibilityReference] 、アクセシビリティ ツリー、要素に適用される ARIA 属性、および計算されたアクセシビリティ プロパティを探索するコントロールがあります。  

#### <a name="accessibility-tree"></a>アクセシビリティ ツリー  

アクセシビリティ **ツリーは ARIA** ツリーとして表示され、 [各][W3CWaiAriaTree] ツリーは DOM 内の `treeitem` 要素に対応します。  ツリーは、選択したノードの計算された役割をアナウンスします。  ツリー内の `div` `span` "GenericContainer" のような汎用的な要素が発表されます。  矢印キーを使用してツリーを走査し、親子関係を探索します。  

**既知の問題**  

*   アクセシビリティ ウィンドウ[で使用される ARIA][W3CWaiAriaTree]ツリーの種類は、VoiceOver のような macOS スクリーン リーダー Microsoft Edgeで適切に公開されない場合があります。 ****  この問題[Chromium進捗#868480][ChromiumIssues868480]通知を受け取る場合は、この問題を購読してください。  
*   **[ARIA 属性**]**** セクションと [計算されたプロパティ] セクションのそれぞれは[ARIA][W3CWaiAriaTree]ツリーとしてマークされますが、それぞれが現在フォーカス管理を行っているのではなく、キーボード操作可能ではありません。  

## <a name="audits-panel"></a>[監査] パネル  

監査 **ツールでは** 、サイトに対して一連のテストを実行して、パフォーマンス、アクセシビリティ、SEO、その他の多くのカテゴリに関連する一般的な問題を確認する必要があります。  

### <a name="configure-and-run-an-audit"></a>監査の構成と実行  

1.  監査ツール**が最初**に開かれると、フォームの最後にある [**** 監査の実行] ボタンにフォーカスが移動します。  既定では、フォームは、シミュレートされた 3G 接続でモバイル エミュレーションを使用してすべてのカテゴリの監査を実行するように構成されています。  
1.  監査 `Shift` + `Tab` 設定を変更するには、参照モードで使用または移動します。  
1.  監査を実行する準備ができたら、[監査の実行] ボタンに戻 **り、** を選択します `Enter` 。  
1.  フォーカスは、監査を終了できる **[キャンセル** ] ボタンを使用してモーダル ウィンドウに移動します。  監査が実行され、ページが複数回更新されると、一連の耳鳴り音が聞こえる場合があります。  

**既知の問題**  

*   構成フォームの異なるセクションは、現在要素でマーク `fieldset` 付けされていない。  参照モードで移動して、各セクションに関連付けられているコントロールを把握する方が簡単な場合があります。  
*   監査の実行が完了すると、耳コンやライブ領域のアナウンスはありません。  通常、所要時間は約 30 秒で、その後、結果に移動できます。  ブラウズ モードを使用すると、結果に最も簡単にアクセスできます。  

### <a name="navigate-the-audit-report"></a>監査レポートを移動する  

監査レポートは、各監査カテゴリに対応するセクションに編成されます。  レポートが開き、各カテゴリのスコアの一覧が表示されます。  これらのスコアは、関連するセクションにスキップするために使用できるリンクです。  各セクション内には、渡された監査または失敗した監査に関連する情報を含む拡張可能 `details` な要素があります。  既定では、失敗した監査だけが表示されます。  各セクションは、渡された `details` 監査のすべてが含まれる最終的な要素で終わります。  

新しい監査を実行するには、レポートを終了し、[監査の実行] `Shift` + `Tab` **ボタンを探します**。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "アクセシビリティ|Microsoft Docs"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "[アクセシビリティ] ウィンドウ - [アクセシビリティ リファレンス] |Microsoft Docs"  
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
